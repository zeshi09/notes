---
title: "Chrome DevTools MCP: Официальный MCP-сервер, CLI и скиллы от команды Chrome DevTools для глубокой отладки в агентах"
repo: "https://github.com/ChromeDevTools/chrome-devtools-mcp"
category: "02_agent_runtimes_and_harnesses"
tags: [chrome-devtools-mcp, google-chrome, mcp, browser-automation, devtools, puppeteer, performance, memory-leak, cli, agent-skills, webmcp]
stars: "56.1k+"
date: 2026-11-14
---

# 🛠️ Chrome DevTools MCP: Полный доступ к Chrome DevTools для coding-агентов

> **Ссылка на репозиторий:** [https://github.com/ChromeDevTools/chrome-devtools-mcp](https://github.com/ChromeDevTools/chrome-devtools-mcp)  
> **Официальная документация:** [https://developer.chrome.com/docs/devtools/agents](https://developer.chrome.com/docs/devtools/agents)  
> **Организация:** ChromeDevTools (Google)  
> **Категория:** `02_agent_runtimes_and_harnesses`  
> **Звёзды GitHub:** 56,089+ ★ (+673 ★ за сутки, Trendshift #5, GitHub Trending #4 2026-11-14)  
> **Стек:** TypeScript, Node.js LTS, Puppeteer, Chrome DevTools Frontend, MCP SDK, GN + Ninja  
> **Лицензия:** Apache-2.0 (`v1.13.0`)

---

## 🎯 1. В чём отличие от обычных Playwright/Puppeteer MCP

Большинство браузерных MCP-серверов умеют только кликать и делать скриншоты. **Chrome DevTools MCP** даёт coding-агенту (Antigravity, Claude Code, Cursor, VS Code Copilot, Gemini CLI, Kimi Code) **инструментарий самого DevTools**: запись трейсов производительности с инсайтами, аудит Lighthouse, разбор кучи (Heap Snapshot) на утечки памяти, source-mapped стек-трейсы консоли, logpoints и сетевое мокирование.

### Инженерные принципы (`docs/design-principles.md`)
* **Token-Optimized:** вместо 50 000 строк сырого JSON сервер возвращает семантические сводки (например, «LCP = 3.2s»).
* **Reference over Value:** тяжёлые артефакты (скриншоты, трейсы, видео/скринкасты) сохраняются в файлы/URI, не забивая контекст.
* **Small, Deterministic Blocks & Self-Healing Errors:** атомарные, компонуемые вызовы и ошибки с контекстом для самоисправления агентом.

---

## 🧩 2. Каталог возможностей (13 групп инструментов)

| Группа | Ключевые инструменты (`docs/tool-reference.md`) |
| :--- | :--- |
| **Input & Navigation** | `click`, `click_at`, `drag`, `fill`, `fill_form`, `hover`, `press_key`, `type_text`, `upload_file`, `handle_dialog`, `new_page`, `navigate_page`, `select_page`, `wait_for`, `close_page` |
| **Debugging & Lighthouse** | `evaluate_script`, `list_console_messages` (с source maps), `get_console_message`, `get_css_styles`, `set_logpoints`, `lighthouse_audit`, `take_snapshot`, `take_screenshot`, `screencast_start`/`stop` |
| **Performance (+ CrUX)** | `performance_start_trace`, `performance_stop_trace`, `performance_analyze_insight` (включая полевые данные Chrome UX Report) |
| **Network & Mocks** | `list_network_requests`, `get_network_request`, `mock_network`, `remove_network_mock` |
| **Memory (14 инструментов)** | `take_heapsnapshot`, `compare_heapsnapshots`, `get_heapsnapshot_summary`, `get_heapsnapshot_dominators`, `get_heapsnapshot_retainers`, `get_heapsnapshot_retaining_paths`, `get_heapsnapshot_duplicate_strings`, `query_heapsnapshot_objects` и др. |
| **Emulation & PWA** | `emulate`, `resize_page`, `install_pwa`, `launch_pwa`, `uninstall_pwa`, `get_os_app_state` |
| **Extensions, WebMCP, Auth** | `install_extension`/`reload_extension`/`trigger_extension_action`, `list_webmcp_tools`/`execute_webmcp_tool`, `configure_webauthn`, `execute_3p_developer_tool` |

Для простых сценариев с минимальным расходом контекста есть флаг **`--slim`**, оставляющий ровно 3 инструмента: `navigate`, `evaluate` и `screenshot`.

---

## 🚀 3. Варианты запуска: MCP, автономный CLI и Agent Skills

### А. MCP-сервер (ленивый старт Chrome при первом вызове инструмента)
```json
{
  "mcpServers": {
    "chrome-devtools": {
      "command": "npx",
      "args": [
        "-y",
        "chrome-devtools-mcp@latest",
        "--no-usage-statistics",
        "--no-performance-crux"
      ]
    }
  }
}
```
> Важно про приватность: статистика использования и отправка URL трейсов в CrUX API **включены по умолчанию**. Их можно отключить флагами `--no-usage-statistics` (или env `CHROME_DEVTOOLS_MCP_NO_USAGE_STATISTICS=1`), `--no-performance-crux`, а проверки обновлений — `CHROME_DEVTOOLS_MCP_NO_UPDATE_CHECKS=1`. Поддерживаются `--headless`, `--isolated`, `--executablePath` и отладка Android.

### Б. Автономный CLI (`chrome-devtools`)
```bash
npm i chrome-devtools-mcp@latest -g
chrome-devtools navigate_page 1 --url "https://developers.chrome.com"
chrome-devtools take_screenshot 1 --filePath screenshot.png
chrome-devtools stop
```

### В. Встроенные Agent Skills и плагины
В репозиторий входят скиллы (`./skills`), обучающие агента профильным сценариям: `chrome-devtools`, `chrome-devtools-cli`, `cookie-debugging`, `debug-optimize-lcp`, `memory-leak-debugging` и `troubleshooting`. Устанавливаются как плагин в Claude Code (`/plugin install chrome-devtools-mcp@chrome-devtools-plugins`), Gemini CLI (`gemini extensions install`) или VS Code/Copilot.

---

## 🔗 4. Синергия с базой знаний

* **Связка с [Modern Web Guidance](file:///home/blackzeshi/Documents/Notes/02_agent_runtimes_and_harnesses/modern-web-guidance.md):** официальный тандем от команды Chrome — `modern-web-guidance` задаёт знания о современной веб-платформе, а `chrome-devtools-mcp` даёт «глаза» и профайлер в живом Chrome для верификации.
* **Связка с [Stealth Browser MCP](file:///home/blackzeshi/Documents/Notes/02_agent_runtimes_and_harnesses/stealth-browser-mcp.md) и [Obscura](file:///home/blackzeshi/Documents/Notes/06_developer_tools_and_apps/obscura.md):** если Stealth Browser / Obscura заточены под обход антиботов и скрейпинг, то Chrome DevTools MCP — эталонный стандарт именно для **разработки, профилирования LCP/памяти, DevTools-отладки и WebMCP**.
