---
title: "Cloudflare Kitesurf: Экспериментальный браузерный движок на Rust + Wasm внутри Cloudflare Workers (без Chrome и контейнеров)"
repo: "https://github.com/cloudflare/kitesurf"
category: "02_agent_runtimes_and_harnesses"
tags: [kitesurf, cloudflare, browser-engine, webassembly, rust, blitz, stylo, cdp, puppeteer, browser-automation, dynamic-workers]
stars: "1.0k+"
date: 2026-11-14
---

# 🪁 Cloudflare Kitesurf: Браузерный движок на Rust + Wasm внутри Cloudflare Workers

> **Ссылка на репозиторий:** [https://github.com/cloudflare/kitesurf](https://github.com/cloudflare/kitesurf)  
> **Официальный сайт:** [https://kitesurf.dev](https://kitesurf.dev)  
> **Организация:** Cloudflare (Open Source, Proof of Concept)  
> **Категория:** `02_agent_runtimes_and_harnesses`  
> **Звёзды GitHub:** 1,063+ ★ (Trendshift #9, 2026-11-14)  
> **Стек:** Rust (`Blitz`, `Stylo`, `Taffy`, `Parley`, `vello_cpu`, `Boa`, `ratatui`), WebAssembly (`wasm-bindgen`), TypeScript, Cloudflare Dynamic Workers (`wrangler`), Bazel, pnpm  
> **Лицензия:** Apache-2.0

---

## 🎯 1. В чём суть: браузер без Chromium и Docker-контейнеров

Обычно облачная браузерная автоматизация для AI-агентов требует тяжёлой инфраструктуры: на каждую сессию или пул воркеров поднимается Linux-контейнер с полноценным Chromium (сотни мегабайт образа, гигабайты RAM, заметный холодный старт).

**Kitesurf** проверяет радикальную альтернативу: **убрать Chrome и контейнеры целиком**, запустив браузерный движок на базе **Rust → WebAssembly** и **V8-субизолятов** прямо внутри Cloudflare Workers. Снаружи движок отдаёт **Chrome DevTools Protocol (CDP)** по WebSocket, поэтому совместим с Puppeteer и самим Chrome DevTools.

---

## 🏗️ 2. Архитектура изоляции и рендеринга

```text
CDP Client (Puppeteer / Chrome DevTools / AI Agent)
       │  ws://127.0.0.1:8787/devtools/browser
       ▼
┌─────────────────────────────────────────────────────────────────────────┐
│ packages/engine (Engine Worker: маршрутизация CDP, оркестрация)         │
└──────────────┬───────────────────────────────────────┬──────────────────┘
               │ Dynamic Worker (env.LOADER)           │ Render Port
               ▼                                       ▼
┌─────────────────────────────────────┐  ┌────────────────────────────────┐
│ Per-Page Sub-Isolate                │  │ packages/page-renderer         │
│ • packages/page-script (навигация)  │  │ (Stateless Raster Worker)      │
│ • packages/dom-shim (DOM + CSSOM)   │  │ • packages/renderer-core (Wasm)│
│ • packages/script-gate (CSP + SRI)  │  │ • vello_cpu (PNG / PDF)        │
│ • packages/core (Rust+Wasm Blitz)   │  └────────────────────────────────┘
│ • packages/worker-script (WebWorker)│
└─────────────────────────────────────┘
```

### Устройство пакетов монорепозитория

| Пакет | Назначение |
| :--- | :--- |
| **`packages/core`** | Ядро на Rust в несколько мегабайт сжатого Wasm на стеке **Blitz**: **Stylo** (CSS-каскад от Servo/Firefox), **Taffy** (layout), **Parley** (текст и шрифты), **`vello_cpu`** (рендер скриншотов и PDF), встроенный JS-движок **Boa**, сетевой провайдер и **`tty_*` + `ratatui`** для терминального рендера. |
| **`packages/engine`** | Входной Worker: принимает WebSocket-соединения CDP, управляет сессиями, оркестрирует субизоляты страниц и загрузку ресурсов. |
| **`packages/page-script`** | Рантайм отдельной страницы, загружаемый через Dynamic Workers (`env.LOADER`) — отвечает за навигацию, выполнение скриптов и CDP DOM/eval. |
| **`packages/dom-shim`** | Реализация браузерных API (`Document`, `Element`, `Node`, `Event`, `CSSOM`) в песочнице поверх Rust-ядра. |
| **`packages/script-gate`** | Политика безопасности исполнения скриптов: проверка **CSP (`script-src`)** и **SRI**. |
| **`packages/page-renderer` + `renderer-core`** | Отдельный stateless worker-растеризатор с уменьшенным Wasm-срезом (`SceneRasterizer`) и кэшем ресурсов. |
| **`packages/worker-script`** | Загрузчик изолированных воркеров для `new Worker()` внутри страницы. |

---

## ⚙️ 3. Статус, ограничения и локальный запуск

* **Proof of Concept:** авторы прямо предупреждают в `AGENTS.md` и `README.md`, что реализация многих веб-стандартов и методов CDP ещё неполная — это не полноценная замена Chrome, а исследовательский движок (но базовые приложения вроде TodoMVC и часть WPT уже проходят).
* **Dynamic Workers:** в облаке Cloudflare требуется тариф **Workers Paid** (доступ к Dynamic Workers для создания субизолятов под каждую страницу). Локально работает бесплатно через `wrangler dev`.

### Быстрый локальный старт (нужны Bazelisk, Node 22+, `pnpm@9.15.4`)
```bash
git clone https://github.com/cloudflare/kitesurf.git
cd kitesurf
pnpm install --frozen-lockfile

# Сборка Wasm-модулей через Bazel и старт локального wrangler dev (порт 8787)
pnpm run dev

# Проверка статуса и подключение CDP-клиентов:
# Health: http://127.0.0.1:8787/health
# CDP:    ws://127.0.0.1:8787/devtools/browser
```

Для встроенного Chrome DevTools frontend (чтобы не упираться в ограничения hosted frontend и `127.0.0.1`):
```bash
bazel run --config=devtools //packages/engine:dev_build
```

---

## 🔗 4. Синергия с базой знаний

* **Связка с [Chrome DevTools MCP](file:///home/blackzeshi/Documents/Notes/02_agent_runtimes_and_harnesses/chrome-devtools-mcp.md) и [Obscura](file:///home/blackzeshi/Documents/Notes/06_developer_tools_and_apps/obscura.md):** Kitesurf — это следующий шаг эволюции headless-браузеров: переход от «лёгкого Chromium в контейнере» к **браузеру-функции в V8-изоляте + Wasm**, говорящему по тому же CDP.
* **Связка с [Monty](file:///home/blackzeshi/Documents/Notes/02_agent_runtimes_and_harnesses/monty.md):** тот же архитектурный принцип — выкинуть тяжёлую ОС-песочницу ради сверхлёгкого встраиваемого рантайма на Rust/Wasm (там для Python, здесь — для веба).
