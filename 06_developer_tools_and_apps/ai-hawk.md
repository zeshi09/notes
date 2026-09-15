---
title: "AIHawk: Скрытный антибот-браузер и агент веб-автоматизации с поддержкой MCP (Undetected Browsing)"
repo: "https://github.com/feder-cr/AIHawk"
category: "06_developer_tools_and_apps"
tags: [ai-hawk, stealth-browser, anti-detect, anti-bot-bypass, mcp, browser-agent, web-automation, computer-use, playwright, cloudflare-bypass, python]
stars: "31.5k+"
date: 2026-09-14
---

# 🦅 AIHawk: Скрытный антибот-браузер и агент веб-автоматизации с поддержкой MCP

> **Ссылка на репозиторий:** [https://github.com/feder-cr/AIHawk](https://github.com/feder-cr/AIHawk)  
> **Автор:** Federico Cafagna (@feder-cr)  
> **Слоган:** *«Anti detect browser and web browsing agent: an open-source MCP server for undetected browsing, AI web scraping and computer use agents. No captchas.»*  
> **Звёзды GitHub:** 31,500+ ★ (Освещался в Wired, TechCrunch, The Verge, Business Insider)  
> **Стек:** Python 3.10+, invisible-playwright, Model Context Protocol (MCP), FastAPI  
> **Совместимость:** Claude Code, Gemini CLI, OpenAI Codex, Antigravity CLI  
> **Лицензия:** MIT / Open-Source  

---

## 🎯 1. В чем проблема традиционных браузерных агентов?

Полноценное использование интернета автономными AI-агентами (Computer Use, сбор данных, автоматизация бизнес-процессов) в 2026 году наталкивается на жесткие системы защиты от ботов:
* **Cloudflare Turnstile, Datadome, Akamai и reCAPTCHA v3:** Мгновенно определяют стандартные автоматизированные драйверы (Puppeteer, классический Playwright, Selenium) по свойствам объекта `navigator.webdriver`, аномалиям рендеринга шрифтов и холста (Canvas fingerprinting), отсутствию аудио-энтропии и специфичным сетевым заголовкам.
* **Механическое поведение:** Боты кликают точно по центру элементов с нулевым временем перемещения курсора, что триггерит поведенческий скоринг систем антифрода.
* **Сложность управления сессиями:** После прохождения авторизации агент перезапускается и теряет все сохраненные токены, снова попадая под блок.

**AIHawk** — это специализированный невидимый браузерный агент на базе модифицированного стелс-движка Firefox (`invisible-playwright`), который управляется на чистом естественном языке и нативно интегрируется с кодинг-агентами через протокол **MCP**.

---

## 🛠️ 2. Архитектура невидимости (Stealth Engine)

```text
┌─────────────────────────────────────────────────────────────┐
│                       AI Coding Agent                       │
│             (Claude Code / Gemini CLI / Codex)              │
└──────────────────────────────┬──────────────────────────────┘
                               │ Model Context Protocol (stdio / uvx)
┌──────────────────────────────▼──────────────────────────────┐
│                    AIHawk MCP Server Core                   │
│                                                             │
│  ┌────────────────────────┐    ┌─────────────────────────┐  │
│  │ Human Behavior Synthes │    │ Fingerprint Masker      │  │
│  │ • Bézier Curve Mouse   │    │ • Canvas/Audio Noise    │  │
│  │ • Jitter & Typo Typing │    │ • Navigator Patching    │  │
│  │ • Organic Scroll Speed │    │ • WebGL Spoofing        │  │
│  └───────────┬────────────┘    └────────────┬────────────┘  │
│              │                              │               │
│  ┌───────────▼──────────────────────────────▼────────────┐  │
│  │ Invisible-Playwright (Stealth Firefox Runtime)        │  │
│  │ - Persistent Profile Storage (~/.aihawk/profiles)     │  │
│  │ - Deterministic Fingerprint Seeds (--seed 1337)       │  │
│  │ - Egress & SOCKS5 / HTTP Proxy Tunneling              │  │
│  └───────────────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────────────┘
```

### Ключевые механизмы обхода защит:
1. **Биометрическая эмуляция движений:** Курсор перемещается по сглаженным кривым Безье с переменным ускорением и микро-дрожанием (Human Jitter). Ввод текста имитирует реальные паузы между нажатиями клавиш.
2. **Низкоуровневая маскировка браузера:** Полное удаление флагов автоматизации из JS-рантайма, гармонизация WebGL, WebRTC и Canvas с реальными аппаратными профилями.
3. **Детерминированный Seed:** Параметр `--seed <число>` гарантирует, что при каждом перезапуске агент имеет в точности один и тот же неизменный цифровой отпечаток устройства, не вызывая подозрений у систем скоринга.
4. **Персистентность сессий:** Папка `--profile-dir` сохраняет авторизованные сессии, cookies и локальное хранилище между вызовами.

---

## 🔌 3. Варианты использования

### Вариант 1: Подключение к ассистенту через MCP
Установка выполняется за пару секунд через `uvx`:
```bash
# 1. Скачивание невидимого рантайма
uvx invisible-playwright fetch

# 2. Подключение к Claude Code
claude mcp add --scope user stealth -- uvx aihawk

# 3. Подключение к Gemini CLI
gemini mcp add --scope user stealth uvx aihawk

# 4. Подключение к Codex
codex mcp add stealth -- uvx aihawk
```

### Вариант 2: Автономный Web UI
AIHawk поставляется со встроенным веб-интерфейсом: слева чат с агентом, справа живая трансляция экрана браузера в реальном времени.
```bash
uvx aihawk ui --openrouter-key sk-or-...
# Открываем http://127.0.0.1:8765 в браузере
```

---

## 💬 4. Пример агентного сценария на естественном языке

После подключения через MCP вы можете отдавать агенту высокоуровневые задачи, требующие сложного взаимодействия с защищенными сервисами:

> **Промпт разработчика в Claude Code:**  
> *«Используй MCP-инструмент stealth. Зайди на сервис бронирования билетов, выбери рейс Милан — Лиссабон на 15 число следующего месяца. Поле выбора даты — это кастомный JS-календарь, поэтому кликни по дате курсором, а не вбивай текст. Собери цены эконом-класса и найди самый выгодный рейс.»*

**Что делает агент:**
1. Запускает скрытную сессию Firefox через `aihawk_open_session`.
2. Переходит по ссылке, плавно прокручивает страницу, обходя фоновые проверки Cloudflare Turnstile.
3. Находит координаты виджета календаря, эмулирует естественное движение курсора и клик.
4. Считывает отрендеренный DOM и возвращает структурированный ответ разработчику.

---

## ⚖️ 5. Сравнение браузерных инструментов в базе знаний

| Инструмент | Стек | Главное назначение | Преимущество |
| :--- | :---: | :--- | :--- |
| **[Obscura](file:///home/blackzeshi/Documents/Notes/06_developer_tools_and_apps/obscura.md)** | Чистый Rust | Headless-браузер для AI-агентов с фокусом на Accessibility Tree | Нулевые накладные расходы, минимальный RAM |
| **[Crawl4AI](file:///home/blackzeshi/Documents/Notes/06_developer_tools_and_apps/crawl4ai.md)** | Python / Playwright | Краулер и генератор чистого Fit Markdown для RAG | BM25-очистка шума, структурированное Pydantic-извлечение |
| **AIHawk** | Python / Stealth Firefox | Автоматизация действий человека (Computer Use) и обход антиботов | **Полная невидимость для Cloudflare/капч**, MCP-сервер |
