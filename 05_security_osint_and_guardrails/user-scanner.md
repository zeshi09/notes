---
title: "User Scanner: Профессиональный OSINT-комбайн по Email и Никнеймам"
repo: "https://github.com/kaifcodec/user-scanner"
category: "05_security_osint_and_guardrails"
tags: [osint, security, digital-footprint, email-recon, username-scanner, python]
stars: "4.5k+"
date: 2026-09-01
---

# 🕵️‍♂️ User Scanner: Профессиональный OSINT-комбайн по Email и Никнеймам

> **Ссылка на репозиторий:** [https://github.com/kaifcodec/user-scanner](https://github.com/kaifcodec/user-scanner)  
> **Автор:** Kaif Codec (@kaifcodec)  
> **Звёзды GitHub:** 4,500+ ★  
> **Сфера:** OSINT, Кибербезопасность, Digital Footprinting, Threat Intelligence  
> **Стек:** Python 3.8+, Asyncio, Aiohttp, Rich  
> **Платформы:** Linux, Windows, macOS, Android (Termux)  
> **Лицензия:** MIT  

---

## 🎯 1. В чем назначение инструмента?

**User Scanner** — это мощный открытый инструмент разведки по открытым источникам (**OSINT 2-in-1**), предназначенный для глубокого сбора цифрового следа (*Digital Footprint*) человека всего по одному параметру: **адресу электронной почты** или **никнейму (username)**.

В отличие от устаревших утилит (вроде классического Sherlock), User Scanner ориентирован на современные платформы, защищенные от спама и требующие сложных сигнатурных проверок.

```text
[ Входные данные: Email или Username ]
                   │
                   ▼
┌────────────────────────────────────────────────────────┐
│               USER SCANNER (465+ VECTORS)              │
│                                                        │
│   📧 Email Scanner (175+ активных векторов):           │
│   • Проверка привязки к Google, GitHub, Spotify,       │
│     Telegram, Twitter, Discord, Amazon, ProtonMail     │
│   • Анализ утечек паролей и баз HaveIBeenPwned         │
│   • Проверка MX/SPF записей и валидности домена        │
│                                                        │
│   👤 Username Scanner (290+ социальных платформ):      │
│   • Социальные сети, форумы, криптокошельки, блоги     │
│   • Поиск профилей на dev-порталах (GitLab, LeetCode)  │
│   • Параллельный асинхронный опрос через aiohttp       │
└────────────────────────┬───────────────────────────────┘
                         │
                         ▼
[ Структурированный отчет: CLI таблица / JSON / HTML / PDF ]
```

---

## 💎 2. Ключевые фичи

1. **465+ активно поддерживаемых векторов сканирования:** Регулярные обновления базы платформ с отслеживанием изменений API.
2. **Высокая скорость (Asyncio / Aiohttp):** Полное сканирование сотен ресурсов занимает 10–25 секунд.
3. **Умная обработка ложных срабатываний (False-Positive Filtration):** Анализ статус-кодов, размера ответов, заголовков и редиректов.
4. **Работа на мобильных устройствах:** Нативная поддержка Android через Termux.

---

## 🚀 3. Быстрый запуск

```bash
# Клонирование и установка зависимостей
git clone https://github.com/kaifcodec/user-scanner.git
cd user-scanner
pip install -r requirements.txt

# Сканирование по никнейму
python user-scanner.py -u username

# Сканирование по Email с экспортом отчета
python user-scanner.py -e target@example.com --export html
```

---
*Заметка сохранена: 2026-09-01 в /home/blackzeshi/Documents/Notes/user-scanner.md*