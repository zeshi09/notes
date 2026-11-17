---
title: "Google Stitch Skills: Официальная библиотека агентных скиллов и плагинов для UI-дизайна и генерации кода через Stitch MCP"
repo: "https://github.com/google-labs-code/stitch-skills"
category: "02_agent_runtimes_and_harnesses"
tags: [stitch-skills, google-labs, agent-skills, mcp, ui-ux, design-system, design-md, react, react-native, remotion, shadcn-ui, antigravity, claude-code, cursor]
stars: "9.2k+"
date: 2026-11-16
---

# 🎨 Google Stitch Skills: Скиллы и плагины для генерации UI и дизайна через Stitch MCP

> **Ссылка на репозиторий:** [https://github.com/google-labs-code/stitch-skills](https://github.com/google-labs-code/stitch-skills)  
> **Настройка Stitch MCP:** [https://stitch.withgoogle.com/docs/mcp/setup](https://stitch.withgoogle.com/docs/mcp/setup)  
> **Организация:** Google Labs (`google-labs-code`)  
> **Категория:** `02_agent_runtimes_and_harnesses`  
> **Звёзды GitHub:** 9,192+ ★ (+248 ★ за сутки, GitHub Trending #3 2026-11-16)  
> **Формат:** Agent Skills Open Standard (`agentskills.io`) + плагины под Codex / Claude Code / Cursor / Antigravity / Gemini CLI / OpenCode  
> **Лицензия:** Apache-2.0

---

## 🎯 1. В чём суть: замкнутый цикл «Код ↔ Stitch Дизайн ↔ Компоненты»

**Stitch Skills** — официальный набор плагинов и скиллов от Google Labs для работы с сервером **Stitch MCP**. Они превращают coding-агента в полноценный фронтенд/дизайн-пайплайн: от улучшения расплывчатого промпта и генерации семантической спецификации `DESIGN.md` до выгрузки существующего фронтенда в Google Stitch и обратной компиляции макетов в React, React Native, Vite-дашборды или видеопрезентации Remotion.

---

## 🧩 2. Три плагина и состав скиллов (`plugins/`)

| Плагин | Скиллы | Что автоматизирует |
| :--- | :--- | :--- |
| **`stitch-design`** | `code-to-design`, `generate-design`, `manage-design-system`, `extract-design-md`, `extract-static-html`, `upload-to-stitch` | Перенос кода React/Vue в Stitch, извлечение self-contained static HTML (с инлайном CSS и картинок), генерация и синхронизация дизайн-систем и загрузка локальных макетов. |
| **`stitch-build`** | `react-components`, `react-native`, `react-vite-dashboard`, `remotion`, `shadcn-ui` | Конвертация экранов Stitch в модульный React (с валидацией токенов), React Native (`StyleSheet` + навигация), Vite-дашборды (TanStack Query + `DESIGN.md` + Web3), `shadcn/ui` и walkthrough-видео через **Remotion**. |
| **`stitch-utilities`** | `design-md`, `enhance-prompt`, `stitch-loop`, `taste-design` | Преобразование проектов Stitch в `DESIGN.md`, прокачка UI-промптов, **автономная генерация многостраничных сайтов с валидацией (`stitch-loop`)** и жёсткие anti-generic правила типографики и цвета (`taste-design`). |

### Анатомия каждого скилла по стандарту `agentskills.io`
```text
skills/<skill-name>/
├── SKILL.md     — «Mission Control» для агента (инструкции и границы)
├── scripts/     — исполняемые валидаторы и скрипты
├── resources/   — чеклисты и стайл-гайды
└── examples/    — синтаксически эталонные примеры
```

---

## 🚀 3. Установка (Codex, Claude Code, Cursor, OpenCode)

Предварительно должен быть настроен удалённый **Stitch MCP** сервер.

```bash
# Codex CLI (добавление marketplace со sparse checkout)
codex plugin marketplace add google-labs-code/stitch-skills --ref main \
  --sparse .agents/plugins \
  --sparse plugins/stitch-design \
  --sparse plugins/stitch-build \
  --sparse plugins/stitch-utilities

# Claude Code (в текущий проект)
npx plugins add google-labs-code/stitch-skills --scope project --target claude-code

# Cursor (в текущий workspace)
npx plugins add google-labs-code/stitch-skills --scope workspace --target cursor

# Выборочная установка конкретных скиллов
npx skills add google-labs-code/stitch-skills
```

> **Нюанс для OpenCode:** при ручном копировании папок в `.opencode/skills/` имена вроде `stitch::generate-design` нужно переименовать в lowercase `kebab-case` (чтобы поле `name` в frontmatter совпадало с именем папки), а встроенные вызовы инструментов адаптировать под `webfetch`/`bash`.

---

## 🔗 4. Синергия с базой знаний

* **Связка с [Awesome DESIGN.md](file:///home/blackzeshi/Documents/Notes/02_agent_runtimes_and_harnesses/awesome-design-md.md), [Impeccable](file:///home/blackzeshi/Documents/Notes/02_agent_runtimes_and_harnesses/impeccable.md) и [Astryx](file:///home/blackzeshi/Documents/Notes/02_agent_runtimes_and_harnesses/astryx.md):** `stitch-skills` унифицирует тот же подход с `DESIGN.md` и борьбой против «вайбкодинг-слопа» (`taste-design`), но привязывает его к живому двустороннему дизайн-серверу через **Stitch MCP** (`extract-design-md`, `code-to-design`, `stitch-loop`).
* **Связка с [Modern Web Guidance](file:///home/blackzeshi/Documents/Notes/02_agent_runtimes_and_harnesses/modern-web-guidance.md):** ещё один официальный эталон структуры `SKILL.md` (с `scripts/`, `resources/`, `examples/`) от команды Google, ориентированный уже на связку «дизайн-инструмент ↔ кодинг-агент».
