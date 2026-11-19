---
title: "AI Agents for Beginners (Microsoft): Открытый 18-урочный практический курс по созданию AI-агентов"
repo: "https://github.com/microsoft/ai-agents-for-beginners"
category: "00_strategy_and_roadmaps"
tags: [ai-agents, microsoft, learning-roadmap, autogen, semantic-kernel, microsoft-agent-framework, agentic-rag, mcp, a2a, context-engineering, agent-memory, computer-use, python, jupyter]
stars: "80.3k+"
date: 2026-11-18
---

# 🎓 AI Agents for Beginners (Microsoft): 18 уроков от основ до продакшена и безопасности

> **Ссылка на репозиторий:** [https://github.com/microsoft/ai-agents-for-beginners](https://github.com/microsoft/ai-agents-for-beginners)  
> **Портал курса:** [https://aka.ms/ai-agents-beginners](https://aka.ms/ai-agents-beginners)  
> **Организация:** Microsoft  
> **Категория:** `00_strategy_and_roadmaps`  
> **Звёзды GitHub:** 80,348+ ★ (26.2k+ форков, Trendshift #23 2026-11-18)  
> **Стек:** Python, Jupyter Notebooks, **Microsoft Agent Framework (MAF)**, Microsoft Foundry Agent Service V2, Semantic Kernel / AutoGen, Foundry Local, OpenAI-совместимые API (в т.ч. MiniMax)  
> **Лицензия:** MIT

---

## 🎯 1. В чём ценность курса

Официальный открытый курс Microsoft из **18 самодостаточных модулей** (текст в `README.md` + короткие видео + `code_samples` на Python/Jupyter). Уроки можно проходить в любом порядке — они закрывают весь жизненный цикл современных агентных систем, включая свежие темы 2025–2026 годов: протоколы **MCP / A2A / NLWeb**, **Context Engineering**, **Agent Memory** (включая `Cognee`), **Computer Use (CUA)**, **локальных агентов (Foundry Local)** и **Securing AI Agents**.

---

## 🗺️ 2. Программа курса (18 уроков по 4 блокам)

```text
[1–4. База и паттерны]         [5–9. Память, RAG и планирование]
  01. Intro & Use Cases            05. Agentic RAG
  02. Agentic Frameworks           06. Trustworthy Agents
  03. Design Patterns              07. Planning Pattern
  04. Tool Use Pattern             08. Multi-Agent Pattern
                                   09. Metacognition (саморефлексия)

[10–14. Протоколы и контекст]  [15–18. CUA, локальный запуск и защита]
  10. Agents in Production         15. Computer Use Agents (CUA / Browser)
  11. Protocols: MCP, A2A, NLWeb   16. Deploying Scalable Agents
  12. Context Engineering          17. Creating Local AI Agents
  13. Managing Agentic Memory      18. Securing AI Agents
  14. Microsoft Agent Framework
```

### Полный список модулей

| № | Папка урока | Фокус |
| :-: | :--- | :--- |
| 01 | `01-intro-to-ai-agents` | Введение в AI-агентов и прикладные кейсы |
| 02 | `02-explore-agentic-frameworks` | Обзор агентных фреймворков и создание агента в Foundry |
| 03 | `03-agentic-design-patterns` | Ключевые паттерны проектирования агентных систем |
| 04 | `04-tool-use` | Подключение инструментов (Tool Use / Function Calling) |
| 05 | `05-agentic-rag` | Agentic RAG и поисковые пайплайны |
| 06 | `06-building-trustworthy-agents` | Надёжность, предсказуемость и доверие к действиям |
| 07 | `07-planning-design` | Декомпозиция задач и паттерн планирования |
| 08 | `08-multi-agent` | Мультиагентные схемы (с примерами и `solution/`) |
| 09 | `09-metacognition` | Метакогниция, критика и самоисправление агента |
| 10 | `10-ai-agents-production` | Вывод агентов в продакшен |
| 11 | `11-agentic-protocols` | Агентные протоколы: **MCP**, **A2A** и **NLWeb** |
| 12 | `12-context-engineering` | Инженерия контекста для длинных траекторий |
| 13 | `13-agent-memory` | Управление памятью (`13-agent-memory.ipynb` + `Cognee`) |
| 14 | `14-microsoft-agent-framework` | Практика на Microsoft Agent Framework (MAF) |
| 15 | `15-browser-use` | Computer Use Agents (CUA) и браузерная автоматизация |
| 16 | `16-deploying-scalable-agents` | Масштабируемое развёртывание в Microsoft Foundry |
| 17 | `17-creating-local-ai-agents` | Полностью локальные агенты через **Foundry Local** |
| 18 | `18-securing-ai-agents` | Безопасность агентных систем |

---

## ⚙️ 3. Быстрый клон без лишних переводов (`sparse-checkout`)

Репозиторий содержит десятки машинных переводов через *Co-op Translator* (`translations/` и `translated_images/`). Чтобы не тянуть гигабайты дублей картинок, авторы рекомендуют клонировать с `sparse-checkout`:

```bash
git clone --filter=blob:none --sparse https://github.com/microsoft/ai-agents-for-beginners.git
cd ai-agents-for-beginners
git sparse-checkout set --no-cone '/*' '!translations' '!translated_images'
```

*(Для запуска примеров используется `.env.example`, DevContainer `.devcontainer/` и Microsoft Foundry или альтернативные OpenAI-совместимые провайдеры, например MiniMax; детали — в `00-course-setup/README.md`.)*

---

## 🔗 4. Синергия с базой знаний

* **Связка с [AI Engineering Hub](file:///home/blackzeshi/Documents/Notes/00_strategy_and_roadmaps/ai-engineering-hub.md):** `AI Agents for Beginners` даёт пошаговый учебный маршрут с видео и базовыми ноутбуками по стандартам Microsoft (MAF, MCP, A2A, CUA), а `AI Engineering Hub` дополняет его 90+ прикладными проектами по RAG, GraphRAG и evals.
* **Связка с [AI Agent Book](file:///home/blackzeshi/Documents/Notes/02_agent_runtimes_and_harnesses/ai-agent-book.md) и [TCB & Reference Monitor](file:///home/blackzeshi/Documents/Notes/05_security_osint_and_guardrails/tcb-agent-security.md):** уроки 12–13 и 18 можно рассматривать как вводную базу перед углублённым изучением харнес-инженерии, изоляции и reference monitor'ов.
