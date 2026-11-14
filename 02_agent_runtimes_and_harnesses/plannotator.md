---
title: "Plannotator: Локальный браузерный и TUI-интерфейс для ревью планов, артефактов, диффов и асинхронного Inbox AI-агентов"
repo: "https://github.com/backnotprop/plannotator"
category: "02_agent_runtimes_and_harnesses"
tags: [plannotator, human-in-the-loop, plan-mode, code-review, annotations, claude-code, codex, opencode, mcp, tui, typescript]
stars: "10.8k+"
date: 2026-11-14
---

# 📝 Plannotator: Визуальный слой ревью, аннотаций и Inbox между человеком и coding-агентами

> **Ссылка на репозиторий:** [https://github.com/backnotprop/plannotator](https://github.com/backnotprop/plannotator)  
> **Официальный сайт:** [https://plannotator.ai](https://plannotator.ai)  
> **Категория:** `02_agent_runtimes_and_harnesses`  
> **Звёзды GitHub:** 10,820+ ★ (+412 ★ за сутки, GitHub Trending #1 2026-11-14)  
> **Стек:** TypeScript, Bun monorepo (`apps/*`, `packages/*`), Browser UI, TUI (`plannotator-tui`), MCP, VS Code extension  
> **Лицензия:** MIT OR Apache-2.0 (v0.28.64)

---

## 🎯 1. В чём идея: вынести ревью из узкого терминала

Читать длинные планы, Markdown-спеки, HTML-прототипы и диффы прямо в потоке терминала неудобно, а писать развёрнутые правки текстом в CLI — медленно. **Plannotator** подключается к coding-агентам через хуки, плагины и MCP и открывает локальный UI в браузере (или TUI в терминале), где вы выделяете фрагменты, оставляете точечные комментарии и в один клик отправляете структурированный фидбэк обратно агенту.

Поддерживаются **Claude Code, Codex, Copilot CLI, Gemini CLI, OpenCode, Kiro, Droid, Amp, DeepSeek Harness, Pi**, а через Inbox — и персональные ассистенты (**Grok Bot, Muse, Hermes, OpenClaw**).

---

## 🏗️ 2. Четыре рабочих контура Plannotator

```text
┌─────────────────────────────────────────────────────────────────────────┐
│                    AI Coding Agents / Personal Assistants               │
│   Claude Code · Codex · OpenCode · Pi · Gemini CLI · Copilot · MCP      │
└───────┬──────────────────┬───────────────────────┬──────────────────────┘
        │ Plan hook        │ Slash / CLI           │ Async / MCP
        ▼                  ▼                       ▼
┌───────────────┐  ┌───────────────────┐  ┌───────────────────────────────┐
│  Plan Mode    │  │ Annotate & Review │  │      Plannotator Inbox        │
│               │  │                   │  │  (`plannotator inbox` / MCP)  │
│ Ревью плана   │  │ • MD, папки, URL  │  │ Единое окно вопросов, файлов, │
│ до старта     │  │ • HTML-артефакты  │  │ скриншотов и ревью от       │
│ правки кода   │  │ • Git/jj/p4/PR    │  │ нескольких агентов без блоки- │
│               │  │   и GitButler     │  │ ровки их сессий               │
└───────┬───────┘  └─────────┬─────────┘  └──────────────┬────────────────┘
        └────────────────────┴───────────────────────────┘
                             │ Структурированный фидбэк
                             ▼
                Следующий ход нужной сессии агента
```

### Основные сценарии и команды
1. **Plan Mode (автоматически по хуку):** как только агент формирует план, Plannotator перехватывает его через hook и открывает окно ревью Markdown-плана до начала редактирования файлов.
2. **Annotate и HTML-артефакты:** разметка локальных файлов, целых папок, веб-страниц, рендер HTML (`--render-html`) и последнего сообщения агента:
   ```bash
   /plannotator-annotate README.md
   /plannotator-annotate src/
   /plannotator-annotate report.html --render-html
   /plannotator-last
   ```
3. **Code Review (диффы и PR/MR):** локальные изменения, GitHub PR, GitLab MR, **GitButler** (весь workspace, стек или слой ветки), **Jujutsu (`jj`)**, **Perforce (`p4`)** и статические патчи (`--patch-file`), плюс встроенный AI-ассистент по диффу:
   ```bash
   /plannotator-review
   /plannotator-review <github-pr-url>
   plannotator review --gitbutler
   plannotator review --patch-file reading.diff
   ```
4. **Plannotator Inbox (`plannotator inbox` / `plannotator inbox mcp`):** локальный «почтовый ящик», куда параллельные агенты складывают вопросы, прикреплённые скриншоты и артефакты, продолжая работу. Ваши ответы маршрутизируются обратно в нужную сессию (в Claude Code, Pi и OpenCode — через плагины как следующий ход, для остальных — через MCP).
5. **Терминальный режим (Herdr Annotate / TUI):** для тех, кто не хочет уходить из терминала (`herdr plugin install plannotator/herdr-annotate` или standalone `plannotator-tui`).

---

## 🔒 3. Приватность и архитектура монорепозитория

* **Local-first без телеметрии:** Plannotator не собирает аналитику использования; планы, диффы, черновики и аннотации хранятся локально (есть команды `plannotator sessions` и `plannotator archive`). Из сетевых запросов по умолчанию происходит только проверка свежих релизов на GitHub при открытии UI.
* **Модульный стек (Bun workspaces):** отдельные плагины под каждый харнес (`apps/hook`, `apps/opencode-plugin`, `apps/pi-extension`, `apps/vscode-extension`, `apps/inbox`, `apps/review`, `apps/relay`, `apps/portal`) и переиспользуемые пакеты (`packages/editor`, `packages/review-editor`, `packages/inbox`, `packages/acp-client`, `packages/t3-code`).

---

## 🔗 4. Синергия с базой знаний

* **Связка с [Whiteboard](file:///home/blackzeshi/Documents/Notes/06_developer_tools_and_apps/whiteboard.md) и [T3 Code](file:///home/blackzeshi/Documents/Notes/02_agent_runtimes_and_harnesses/t3code.md):** Plannotator закрывает именно цикл *двусторонней разметки* (план / артефакт / код-ревью / асинхронный Inbox), превращая человеческие пометки на полях в детерминированный ввод для следующего шага агента.
* **Связка с [Open Code Review](file:///home/blackzeshi/Documents/Notes/02_agent_runtimes_and_harnesses/open-code-review.md):** если Open Code Review автоматизирует первичное AI-ревью, то Plannotator выступает интерактивной поверхностью для финального ревью человеком с возвратом правок агенту.
