---
title: "Diagram Design: 39 журнальных типов диаграмм на чистом HTML+SVG для AI-агентов"
repo: "https://github.com/cathrynlavery/diagram-design"
category: "02_agent_runtimes_and_harnesses"
tags: [data-visualization, diagrams, html, svg, ai-agents, claude-code, codex, no-mermaid]
stars: "30.2k+"
date: 2026-09-03
---

# 📊 Diagram Design: 39 журнальных типов диаграмм на чистом HTML+SVG для AI-агентов

> **Ссылка на репозиторий:** [https://github.com/cathrynlavery/diagram-design](https://github.com/cathrynlavery/diagram-design)  
> **Автор:** Cathryn Lavery (@cathrynlavery)  
> **Слоган:** *«Editorial diagrams your designer won’t hate. No shadows. No Mermaid slop.»*  
> **Звёзды GitHub:** 30,200+ ★ (Топ-3 месячного чарта Trendshift)  
> **Стек:** 100% чистый самодостаточный HTML + inline SVG, CSS Grid/Flexbox  
> **Совместимость:** Claude Code, Cursor, OpenAI Codex, Antigravity, Pi  
> **Лицензия:** MIT  

---

## 🎯 1. В чем идея и почему НЕ Mermaid?

Стандартный инструмент визуализации в нейросетях — Mermaid.js. Но у него есть фундаментальные проблемы при работе с кодинг-агентами:
* Модели часто генерируют синтаксические ошибки, из-за которых вся схема падает в красный экран ошибки.
* Схемы Mermaid выглядят неряшливо: уродливые тени, слипающиеся стрелки, плохая типографика и отсутствие адаптивности.

**Diagram Design** предлагает кардинально иной стандарт для AI-агентов:  
Коллекцию из **39 специализированных грамматик верстки на чистом HTML + SVG**:
* **Нулевые внешние библиотеки:** Не требуется подключать JS-бандлы (самодостаточный рендеринг в любом браузере, WebView и чате).
* **Журнальная эстетика:** Выверенная типографика, гармоничные палитры, поддержка темной и светлой тем, идеальное масштабирование.
* **Агентная семантика:** Разделение поведения и визуального слоя — агент может описать сложную очередь или пайплайн обработки без геометрических ошибок.

---

## 📐 2. Поддерживаемые типы диаграмм (39 вариантов)

```text
┌────────────────────────────────────────────────────────────────────────┐
│                      39 EDITORIAL DIAGRAM GRAMMARS                     │
│                                                                        │
│  🏛 АРХИТЕКТУРА И СИСТЕМЫ:                                             │
│  • C4 Architecture / System Topology (микросервисы, базы, шлюзы)       │
│  • The Loop: Flywheels with shared-memory hub (циклы обратной связи)   │
│  • Deployment & Cloud Infrastructure (Kubernetes, Edge, CDN)           │
│                                                                        │
│  🌊 ПОТОКИ ДАННЫХ И ПРОЦЕССЫ:                                          │
│  • Sankey Diagrams (распределение бюджетов, токенов, трафика)          │
│  • Sequence & Data-Flow Diagrams (последовательность вызовов API)      │
│  • Pipeline & Stage Progression (CI/CD конвейеры)                      │
│                                                                        │
│  🎯 АНАЛИТИКА И СТРАТЕГИЯ:                                             │
│  • Wardley Maps (стратегическое картирование цепочек ценности)         │
│  • Fishbone / Ishikawa Diagrams (поиск первопричин сбоев)              │
│  • User Journey & Story Maps (пользовательский опыт)                   │
│                                                                        │
│  💾 ДАННЫЕ И КОД:                                                      │
│  • Database Schema & ERD (таблицы, внешние ключи, связи 1:N)           │
│  • Dependency Graphs & UML Class Diagrams                              │
└────────────────────────────────────────────────────────────────────────┘
```

---

## 🚀 3. Как использовать с AI-агентами?

1. Подключите скилл к своему терминальному агенту (в каталог `.agents/skills`):
   ```bash
   git clone --depth 1 https://github.com/cathrynlavery/diagram-design.git .agents/skills/diagram-design
   ```
2. Попросите агента:
   > *«Опиши архитектуру нашего воркспейса в формате Diagram Design (System Topology) на чистом HTML. Сделай акцент на связи агента с базой данных и очередью сообщений».*
3. Агент сгенерирует самодостаточный HTML-файл, который открывается в браузере с плавной векторной графикой и кристально четким экспортом в SVG/PNG.

---
*Заметка сохранена: 2026-09-03 в /home/blackzeshi/Documents/Notes/02_agent_runtimes_and_harnesses/diagram-design.md*
