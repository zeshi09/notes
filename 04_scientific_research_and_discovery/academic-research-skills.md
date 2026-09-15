---
title: "Academic Research Skills: Полный цикл научных исследований для Claude Code"
repo: "https://github.com/Imbad0202/academic-research-skills"
category: "04_scientific_research_and_discovery"
tags: [academic-research, claude-code, scientific-writing, peer-review, latex, citation-audit, socratic-planning]
stars: "45.5k+"
date: 2026-09-02
---

# 🎓 Academic Research Skills: Полный цикл научных исследований для Claude Code

> **Ссылка на репозиторий:** [https://github.com/Imbad0202/academic-research-skills](https://github.com/Imbad0202/academic-research-skills)  
> **DOI:** [10.5281/zenodo.20696614](https://doi.org/10.5281/zenodo.20696614)  
> **Автор:** Imbad0202  
> **Звёзды GitHub:** 45,500+ ★ (Топ-5 суточного чарта Trendshift)  
> **Совместимость:** Claude Code CLI (v3.7.0+), VS Code, JetBrains, Antigravity  
> **Лицензия:** CC BY-NC 4.0  

---

## 🎯 1. В чем суть проекта?

**Academic Research Skills (ARS)** — это комплексная открытая библиотека навыков для терминального агента **Claude Code**, автоматизирующая полный сквозной конвейер академической научной работы: **от формулирования идеи статьи до ее верстки в LaTeX и симуляции жесткого рецензирования (Peer-Review)**.

Главный девиз проекта:  
> *«AI is your copilot, not your ghostwriter» (ИИ — ваш второй пилот, а не автор за вас).*

ARS спроектирован так, чтобы предотвратить галлюцинации, вымышленные ссылки и поверхностный текст.

---

## 🔄 2. Сквозной пайплайн академической работы

```text
┌────────────────────────────────────────────────────────────────────────┐
│                 ACADEMIC RESEARCH SKILLS WORKFLOW                      │
│                                                                        │
│  1. 🧠 /ars-plan (Сократовский диалог):                                │
│     • Детальный разбор структуры статьи через наводящие вопросы        │
│     • Формулирование гипотезы, новизны (Novelty) и границ исследования │
│                                                                        │
│  2. 🔎 /ars-search (Поиск литературы и фактчекинг):                    │
│     • Поиск первоисточников в Semantic Scholar, PubMed, arXiv          │
│     • Проверка подлинности цитат и DOI                                 │
│                                                                        │
│  3. ✍️ /ars-write (Академическое написание):                           │
│     • Генерация структурированных разделов статьи в LaTeX/Markdown     │
│     • Строгий научный стиль без клише и канцелярита                    │
│                                                                        │
│  4. 🧐 /ars-review (Симуляция рецензента):                             │
│     • Критический аудит методологии по критериям Nature / NeurIPS      │
│     • Поиск логических дыр, слабых графиков и необоснованных тезисов   │
│                                                                        │
│  5. 🛠 /ars-revise & /ars-bib (Правка и библиография):                 │
│     • Доработка текста по замечаниям рецензента                        │
│     • Экспорт выверенного BibTeX файла с валидированными записями      │
└────────────────────────────────────────────────────────────────────────┘
```

---

## 🚀 3. Быстрая установка в Claude Code

Установка выполняется одной командой в Claude Code CLI:

```text
/plugin marketplace add Imbad0202/academic-research-skills
/plugin install academic-research-skills
```

После установки в терминале становятся доступны слеш-команды `/ars-plan`, `/ars-search`, `/ars-write`, `/ars-review`.

---
*Заметка сохранена: 2026-09-02 в /home/blackzeshi/Documents/Notes/04_scientific_research_and_discovery/academic-research-skills.md*
