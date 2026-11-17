---
title: "NVIDIA SkillEvaluator: Трёхуровневый фреймворк валидации, дедупликации и A/B-оценки агентных скиллов"
repo: "https://github.com/NVIDIA/SkillEvaluator"
category: "02_agent_runtimes_and_harnesses"
tags: [skillevaluator, nvidia, agent-skills, skill-evals, quality-gates, deduplication, harbor, sandboxing, skillspector, claude-code, codex, python]
stars: "1.5k+"
date: 2026-11-16
---

# 🧪 NVIDIA SkillEvaluator: Трёхуровневый конвейер проверки и eval-оценки Agent Skills

> **Ссылка на репозиторий:** [https://github.com/NVIDIA/SkillEvaluator](https://github.com/NVIDIA/SkillEvaluator)  
> **Документация:** [https://docs.nvidia.com/skills/skillevaluator/](https://docs.nvidia.com/skills/skillevaluator/)  
> **Статья (arXiv):** [arXiv:2608.20614](https://arxiv.org/abs/2608.20614)  
> **Организация:** NVIDIA (часть пайплайна `NVIDIA/skills`, статус *Experimental*)  
> **Категория:** `02_agent_runtimes_and_harnesses`  
> **Звёзды GitHub:** 1,515+ ★ (+205 ★ за сутки, GitHub Trending 2026-11-16)  
> **Стек:** Python 3.12–3.14 (`uv`, PyPI `skillevaluator`), SkillSpector, Gitleaks, Semgrep, Harbor, Docker  
> **Лицензия:** Apache-2.0

---

## 🎯 1. В чём суть: превратить `SKILL.md` из текста в проверяемый артефакт

С ростом числа агентных скиллов (по стандарту `agentskills.io`) возникают три проблемы: небезопасные/сломанные скиллы, дублирование инструкций в каталоге и отсутствие доказательств, что скилл **реально помогает агенту**, а не тратит контекст впустую. **SkillEvaluator** решает это трёхуровневым пайплайном с независимыми гейтами.

```text
Skill Folder (SKILL.md + scripts + evals)
   │
   ▼
┌─────────────────────────────────────────────────────────────────────────┐
│ Tier 1: Validation (Статика, безопасность, рубрика качества)            │
│ • Quality-check (без API и Docker, порог по умолчанию 70/100)           │
│ • PII / License / Unicode smuggling / Harness compatibility             │
│ • Интеграция SkillSpector + Gitleaks (+ опционально Semgrep)            │
└───────────────────────────────┬─────────────────────────────────────────┘
                                │ Gate passed
                                ▼
┌─────────────────────────────────────────────────────────────────────────┐
│ Tier 2: Deduplication (Эмбеддинги и семантический анализ пересечений)   │
│ • Поиск дублей внутри скилла (intra_skill) и по каталогу (--catalog)   │
└───────────────────────────────┬─────────────────────────────────────────┘
                                │
                                ▼
┌─────────────────────────────────────────────────────────────────────────┐
│ Tier 3: Live Evaluation (A/B прогон реального агента в песочнице Harbor)│
│ • Автогенерация синтетических кейсов (create-eval-dataset)             │
│ • Сравнение выполнения задач с подключённым скиллом и без него          │
└─────────────────────────────────────────────────────────────────────────┘
```

---

## 🏗️ 2. Что делает каждый уровень и CLI-пайплайн

1. **Tier 1 (`tier1` / `quality-check` / `rubric-eval`):**
   - `quality-check` работает полностью офлайн (без LLM-ключей и Docker): проверяет структуру, совместимость с харнесами, лицензии, утечки PII и `unicode_smuggle_patterns`.
   - Для безопасности автоматически подтягивает верифицированные релизы **`SkillSpector`** и **`Gitleaks`** (плюс опционально `Semgrep`). Если сканер не смог запуститься, статус остаётся `INCOMPLETE`, а не «зелёным».
   - `rubric-eval` оценивает качество документации через LLM (поддерживает в том числе бесплатное прототипирование через `NVIDIA_API_KEY` и `nv_build`).
2. **Tier 2 (`tier2`):**
   - Извлекает эмбеддинги (`src/skillevaluator/embedding/`) и находит перекрытия инструкций внутри самого скилла и по общему реестру `--catalog ./skill-catalog.json`. Блокирует пайплайн, если не передан `--no-block-on-dedup`.
3. **Tier 3 (`tier3` + `create-eval-dataset`):**
   - Генерирует датасет оценочных задач из `evals/EVAL.md`, `--prompt` или сохранённых трасс (или в режиме autopilot из самого скилла).
   - Запускает реального агента (Claude Code, Codex и др.) в изолированной песочнице **[Harbor](https://github.com/harbor-framework/harbor)** (Docker по умолчанию) и замеряет дельту качества **with skill vs without skill**.

---

## 🚀 3. Быстрый старт и CI-интеграция

```bash
# Установка CLI
pip install skillevaluator

# Бесключевая статическая проверка качества (без LLM, Docker и GPU)
uv run --python 3.13 skillevaluator quality-check \
  src/skillevaluator/tier3/reference_skills/text-analyzer \
  -r cli -r json -o reports/first-quality

# Полная проверка Tier 1 (со сканерами, без LLM-рубрики)
skillevaluator validate ./my-skill --tiers 1 --no-llm

# Проверка окружения и прогон всех 3 уровней
uv run --python 3.13 --extra all skillevaluator doctor --env-mode docker
uv run --python 3.13 --extra all skillevaluator validate ./my-skill

# Инициализация GitHub Actions PR-чеков (есть также шаблоны для GitLab)
skillevaluator ci init

# Подключение самого SkillEvaluator как скилла для агента
npx skills add NVIDIA/SkillEvaluator
```

---

## 🔗 4. Синергия с базой знаний

* **Прямая пара со [SkillSpector](file:///home/blackzeshi/Documents/Notes/05_security_osint_and_guardrails/skillspector.md):** SkillSpector отвечает внутри Tier 1 за security-сканирование скиллов (supply-chain / prompt injection), а SkillEvaluator расширяет это до полноценного жизненного цикла: качество → дедупликация → поведенческий A/B-бенчмарк в Docker.
* **Связка с [Modern Web Guidance](file:///home/blackzeshi/Documents/Notes/02_agent_runtimes_and_harnesses/modern-web-guidance.md) и [Agent-Skills (Tech Leads Club)](file:///home/blackzeshi/Documents/Notes/02_agent_runtimes_and_harnesses/agent-skills.md):** эталонная инженерная обвязка для любого корпоративного или open-source каталога `SKILL.md`.
