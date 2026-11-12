---
title: "Addy Osmani Agent Skills: 25 инженерных скиллов полного SDLC-цикла с анти-рационализацией и верификацией"
repo: "https://github.com/addyosmani/agent-skills"
category: "02_agent_runtimes_and_harnesses"
tags: [agent-skills, addy-osmani, sdlc, anti-rationalization, verification-gates, tdd, code-review, claude-code, antigravity, codex, cursor]
stars: "116.6k+"
date: 2026-11-13
---

# 🛠️ Addy Osmani Agent Skills: Production-Grade инженерная дисциплина для кодинг-агентов

> **Ссылка на репозиторий:** [https://github.com/addyosmani/agent-skills](https://github.com/addyosmani/agent-skills)  
> **Авторы:** Addy Osmani, Federico Bartoli, Joan León  
> **Категория:** `02_agent_runtimes_and_harnesses`  
> **Звёзды GitHub:** 116,500+ ★ (+645 ★ за сутки)  
> **Стек:** `SKILL.md` (25 скиллов), 9 slash-команд, 4 персоны ревьюеров, 7 чеклистов, 25 evals и 13 скриптов валидации  
> **Лицензия:** MIT

---

## 🎯 1. В чём идея: От «кратчайшего пути» LLM к дисциплине Senior-инженера

Без жёсткого каркаса AI-агенты склонны срезать углы: сразу писать код без спецификации, подменять тесты заглушками, пропускать ревью безопасности и убеждать пользователя, что «всё работает», хотя сборка даже не запускалась.

**`addyosmani/agent-skills`** кодирует инженерную культуру Google (*Software Engineering at Google* и *Google Engineering Practices*) в виде **25 исполняемых рабочих процессов** — 24 специализированных скилла по всему жизненному циклу разработки + мета-скилл `using-agent-skills` для маршрутизации задач.

```
  DEFINE          PLAN           BUILD          VERIFY         REVIEW          SHIP
 ┌──────┐      ┌──────┐      ┌──────┐      ┌──────┐      ┌──────┐      ┌──────┐
 │ Idea │ ───▶ │ Spec │ ───▶ │ Code │ ───▶ │ Test │ ───▶ │  QA  │ ───▶ │  Go  │
 │Refine│      │  PRD │      │ Impl │      │Debug │      │ Gate │      │ Live │
 └──────┘      └──────┘      └──────┘      └──────┘      └──────┘      └──────┘
  /spec          /plan          /build        /test         /review       /ship
```

---

## 🏗️ 2. Анатомия скилла и 9 команд жизненного цикла

Каждый `SKILL.md` построен не как памятка, а как **процесс с жёсткими гейтами выхода**:
* **Overview & When to Use** — точные триггеры активации.
* **Process** — пошаговый алгоритм с контрольными точками.
* **Rationalizations Table (Анти-рационализация)** — таблица типичных отмазок LLM (например, *«Я допишу тесты позже»*, *«Это тривиальное изменение, ревью не нужно»*) с готовыми контраргументами.
* **Red Flags** — маркеры того, что агент отклонился от процесса.
* **Verification** — обязательные доказательства (логи тестов, вывод линтера, метрики DevTools).

### 9 команд-оркестраторов и 25 скиллов

| Фаза SDLC | Команды | Ключевые скиллы внутри |
| :--- | :--- | :--- |
| **Define** | `/spec`, `/constraints` | `interview-me` (интервью по 1 вопросу до 95% ясности), `idea-refine`, `spec-driven-development`, `constraint-driven-development` (`CONSTRAINTS.md`) |
| **Plan** | `/plan` | `planning-and-task-breakdown` (атомарные задачи с критериями приёмки) |
| **Build** | `/build`, `/build auto` | `incremental-implementation`, `test-driven-development` (пирамида 80/15/5, DAMP over DRY, правило Бейонсе), `context-engineering`, `source-driven-development`, `doubt-driven-development`, `frontend-ui-engineering`, `api-and-interface-design` (закон Хайрума) |
| **Verify** | `/test` | `browser-testing-with-devtools` (Chrome DevTools MCP), `debugging-and-error-recovery` |
| **Review** | `/review`, `/webperf`, `/code-simplify` | `code-review-and-quality` (5 осей, диффы ~100 строк), `code-simplification` (Забор Честертона, Rule of 500), `security-and-hardening`, `performance-optimization` |
| **Ship** | `/ship` | `git-workflow-and-versioning`, `ci-cd-and-automation`, `deprecation-and-migration`, `documentation-and-adrs`, `observability-and-instrumentation`, `shipping-and-launch` |

Особо выделяется скилл **`doubt-driven-development`** — принудительный состязательный пересмотр каждого нетривиального решения со свежим контекстом по цепочке `CLAIM → EXTRACT → DOUBT → RECONCILE → STOP`.

---

## 🧩 3. Персоны, чеклисты и кросс-агентные адаптеры

* **4 специализированные персоны (`agents/`):** `code-reviewer`, `test-engineer`, `security-auditor`, `web-performance-auditor` (со строгим правилом «персоны не вызывают другие персоны» для избежания бесконечных циклов).
* **7 справочных чеклистов (`references/`):** `definition-of-done.md`, `testing-patterns.md`, `security-checklist.md`, `performance-checklist.md`, `accessibility-checklist.md`, `observability-checklist.md`, `orchestration-patterns.md`.
* **Нативные адаптеры в одном репо:** `.claude-plugin/` + `.claude/commands/` + `hooks/`, `.gemini/commands/`, `commands/` + `plugin.json` (Antigravity CLI), `.codex-plugin/`, а также гайды для Cursor, Windsurf, OpenCode, GitHub Copilot и Command Code.

> **Важный нюанс установки:** при точечной установке через `npx skills add ... --skill <name>` копируется только папка `skills/<name>/` без общей директории `references/`. Для полноценной работы со всеми чеклистами лучше ставить весь плагин или клонировать репозиторий целиком.

---

## 💻 4. Быстрый старт

```bash
# Универсальная установка всех 25 скиллов (70+ агентов)
npx skills add addyosmani/agent-skills

# Установка плагином в Antigravity CLI
agy plugin install https://github.com/addyosmani/agent-skills.git

# Установка плагином в Claude Code
/plugin marketplace add addyosmani/agent-skills
/plugin install agent-skills@addy-agent-skills
```

---

## 💡 5. Главные инженерные выводы

1. **Таблицы анти-рационализации реально закрывают поведенческие дыры LLM:** вместо абстрактного «пиши качественно» скилл перехватывает конкретные паттерны самообмана модели на этапе генерации.
2. **Адаптерный слой вокруг общего ядра `skills/`:** сохранение единой портативной базы инструкций с тонкими обёртками под Claude Code, Codex, Antigravity и Cursor решает проблему фрагментации форматов команд.
3. **Инженерия как процесс верификации:** режим `/build auto` убирает ручное подтверждение между атомарными шагами, но никогда не отключает TDD и проверку доказательств на каждом коммите.
