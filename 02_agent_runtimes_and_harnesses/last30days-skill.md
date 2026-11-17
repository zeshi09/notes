---
title: "/last30days (last30days-skill): Агентный скилл глубокого ресерча живых обсуждений и трендов за последние 30 дней"
repo: "https://github.com/mvanhorn/last30days-skill"
category: "02_agent_runtimes_and_harnesses"
tags: [last30days, agent-skills, deep-research, osint, reddit, twitter, hackernews, polymarket, youtube, claude-code, codex, python]
stars: "68.0k+"
date: 2026-11-18
---

# 🗓️ `/last30days`: Агентный скилл ресерча «по людям, а не редакторам» за 30 дней

> **Ссылка на репозиторий:** [https://github.com/mvanhorn/last30days-skill](https://github.com/mvanhorn/last30days-skill)  
> **Спецификация рантайма:** `skills/last30days/SKILL.md` (пайплайн v4)  
> **Категория:** `02_agent_runtimes_and_harnesses`  
> **Звёзды GitHub:** 68,013+ ★ (GitHub Trending #1 / #9)  
> **Стек:** Python (`ThreadPoolExecutor`), Node.js (встроенный клиент Bird для X), OpenAI / xAI API, Agent Skills (`agentskills.io`)  
> **Лицензия:** MIT

---

## 🎯 1. В чём суть: сквозной поиск через закрытые друг от друга платформы

Обычный поиск (Google и встроенный web search у LLM) отстаёт от реальности и отдаёт SEO-статьи вместо живого опыта сообщества. При этом сами платформы фрагментированы: у ChatGPT есть Reddit, но нет X/TikTok; у Gemini есть YouTube, но нет Reddit; у Claude нативно нет ни одной из них.

**`/last30days`** связывает все ключевые площадки в одном агентном пайплайне (с поддержкой Claude Code, Codex, Cursor, Copilot, Gemini CLI, OpenClaw, Grok и др.), ищет строго в окне последних **30 дней**, взвешивает находки по **реальной вовлечённости** (апвоуты, лайки, комментарии, ставки реальными деньгами) и синтезирует короткий бриф с пруфами.

---

## 🏗️ 2. Архитектура пайплайна (`docs/how-search-works.md`)

```text
User: /last30days "topic or person"
   │
   ▼  Parallel Fetch (ThreadPoolExecutor)
┌──────────────────────┬───────────────────────┬──────────────────────────┐
│ Reddit               │ X / Twitter           │ HN · Polymarket · GitHub │
│ (OpenAI web_search   │ (Bundled Bird GraphQL │ YouTube · TikTok · Reels │
│  site:reddit.com)    │  по кукам или xAI)    │ arXiv · Techmeme · Digg  │
└──────────┬───────────┴──────────┬────────────┴────────────┬─────────────┘
           │                      │                         │
           ▼ Enrichment           │                         │
  GET .../comments/{id}/.json     │ (реальные likes/reposts)│
  (score, upvote_ratio, top-10    │                         │
   comments, created_utc)         │                         │
           └──────────────────────┴─────────────────────────┘
                                  │
                                  ▼
                [MERGE -> NORMALIZE -> FILTER -> SCORE -> DEDUPE]
                                  │
                                  ▼
                     Grounded Brief (SKILL.md Agent)
```

### Главные инженерные особенности
1. **Enrichment вместо пересказов:** для Reddit после первичного поиска пайплайн отдельно обращается к открытому JSON-эндпоинту каждого треда (`GET https://reddit.com/r/{sub}/comments/{id}/{slug}/.json` без API-ключа) и забирает точные метрики (`score`, `upvote_ratio`, количество комментариев, топ-10 ответов и `created_utc`).
2. **Два бэкенда для X/Twitter с автовыбором:** приоритетно использует встроенный обрезанный GraphQL-клиент **Bird** (бесплатно, по `AUTH_TOKEN` и `CT0` из env без всплывающих окон), а при их отсутствии — платный `xAI API` (`grok` с `x_search`).
3. **Пресеты глубины поиска:** `--quick` (15–25 тредов, таймаут 90с), default (30–50 тредов, 120с), `--deep` (70–100 тредов, 180с).

---

## 📊 3. Источники данных

* **Zero config (работают сразу и бесплатно):** Reddit, Hacker News, **Polymarket** (вероятности событий, подкреплённые деньгами), GitHub (PR velocity, релизы, issues/discussions), а также `arXiv`, `Techmeme`, `Yahoo Finance` и `Digg` (через `*-pp-cli`).
* **Подключаются мастером настройки / ключами:** X/Twitter, YouTube (поиск по полным транскриптам роликов), TikTok, Instagram Reels, LinkedIn.

---

## 🚀 4. Установка

```bash
# Claude Code (через marketplace с автообновлением)
/plugin marketplace add mvanhorn/last30days-skill
/plugin install last30days

# Codex, Cursor, Copilot, Gemini CLI и 50+ Agent Skills хостов
npx skills add mvanhorn/last30days-skill -g
```

---

## 🔗 5. Синергия с базой знаний

* **Связка с [Agent-Reach](file:///home/blackzeshi/Documents/Notes/02_agent_runtimes_and_harnesses/agent-reach.md):** если Agent-Reach даёт агенту универсальный транспорт для чтения Twitter/Reddit/YouTube/GitHub без API-затрат, то `last30days` добавляет **специализированный 30-дневный временной фильтр, enrichment метрик вовлечённости, Polymarket и единый ранжируемый бриф**.
* **Связка с [Horizon](file:///home/blackzeshi/Documents/Notes/06_developer_tools_and_apps/horizon.md):** `Horizon` работает как фоновый периодический радар инфополя, а `/last30days` — как on-demand OSINT/ресерч по конкретной теме или человеку перед встречей или стартом проекта.
