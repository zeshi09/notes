---
title: "Utopia: Open-Source Enterprise World Model & Ontology Workbench"
repo: "https://github.com/deeplethe/utopia"
category: "03_knowledge_graphs_and_ontologies"
tags: [ontologies, world-model, rust, local-first, mcp, knowledge-graphs]
stars: "1.3k+"
date: 2026-09-01
---

# 🏛️ Utopia: Open-Source Enterprise World Model & Ontology Workbench

> **Ссылка на репозиторий:** [https://github.com/deeplethe/utopia](https://github.com/deeplethe/utopia)  
> **Официальный сайт:** [https://utopia.bi](https://utopia.bi)  
> **Разработчик:** DeepLethe  
> **Звёзды GitHub:** 1,300+ ★  
> **Стек:** 100% чистый Rust, WebAssembly, SQLite, MCP, React  
> **Лицензия:** Apache-2.0  

---

## 🎯 1. Введение и концепция

**Utopia** позиционируется как **«Первая открытая модель мира для предприятий»** (*Open-Source Enterprise World Model*). Это локальное (*Local-First*) рабочее пространство, которое преобразует разрозненные корпоративные документы (PDF, Word, Excel, Markdown, базы данных) в **структурированные онтологии и семантические графы знаний**, с которыми могут безопасно работать AI-агенты.

### Главная проблема, которую решает Utopia:
Обычный RAG и векторный поиск не понимают логических связей бизнеса (кто кому подчиняется, какие регламенты к каким отделам применимы, как рассчитываются KPI). Utopia извлекает из документов не просто фрагменты текста, а **строгую онтологическую схему сущностей, правил и взаимосвязей**.

```text
[ Корпоративные документы (PDF, DOCX, XLSX, DB) ]
                         │
                         ▼
┌────────────────────────────────────────────────────────┐
│                   UTOPIA RUST WORKBENCH                │
│                                                        │
│   • Semantic Parsing & Entity Recognition              │
│   • Автоматическое построение онтологий (OWL/RDF)      │
│   • Детекция конфликтов и валидация связей             │
│   • Local-First: данные не покидают ваш сервер         │
└────────────────────────┬───────────────────────────────┘
                         │
                         ▼
┌────────────────────────────────────────────────────────┐
│                 ENTERPRISE WORLD MODEL                 │
│   • Единый проверяемый источник истины                 │
│   • Доступ для агентов через Model Context Protocol    │
└────────────────────────────────────────────────────────┘
```

---

## 💎 2. Ключевые возможности

1. **Local-First & Высокая производительность на Rust:** Ядро написано на чистом Rust со встроенной базой SQLite и векторным индексом, обеспечивая обработку документов со скоростью сотен страниц в секунду без облачных сервисов.
2. **Model Context Protocol (MCP) интеграция:** Встроенный MCP-сервер позволяет подключать построенную онтологию напрямую к Claude Code, Codex, Cursor и Antigravity.
3. **Визуальный редактор графов и онтологий:** Интерактивный веб-интерфейс для просмотра и ручной корректировки извлеченных связей и сущностей.

---

## 🚀 3. Быстрый запуск

```bash
# Запуск через Docker
docker run -d -p 8080:8080 ghcr.io/deeplethe/utopia:latest

# Или сборка из исходников на Rust
git clone https://github.com/deeplethe/utopia.git
cd utopia
cargo run --release
```

---
*Заметка сохранена: 2026-09-01 в /home/blackzeshi/Documents/Notes/utopia.md*