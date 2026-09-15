---
title: "Dormice: «SQLite среди песочниц» — Self-Hosted долгоживущие песочницы для AI-агентов"
repo: "https://github.com/BitMiracle-AI/Dormice"
category: "02_agent_runtimes_and_harnesses"
tags: [agent-sandbox, self-hosted, e2b-compatible, gvisor, docker, typescript, idle-zero-cost]
stars: "1.0k+"
date: 2026-09-04
---

# 🐭 Dormice: «SQLite среди песочниц» для AI-агентов

> **Ссылка на репозиторий:** [https://github.com/BitMiracle-AI/Dormice](https://github.com/BitMiracle-AI/Dormice)  
> **Слоган:** *«The SQLite of agent sandboxes — one machine, sandboxes that live forever, idle costs nothing.»*  
> **Звёзды GitHub:** 1,000+ ★  
> **Стек:** TypeScript, Node.js, Docker + gVisor, SQLite ledger, E2B-compatible API  
> **Лицензия:** Apache-2.0  

---

## 🎯 1. В чем проблема облачных песочниц (E2B, Modal)?

Облачные платформы песочниц тарифицируют каждую секунду существования виртуальной машины. Поэтому разработчикам приходится делать песочницы одноразовыми: запустил скрипт, убил контейнер, потерял состояние диска, склонированные репозитории и кэши `pip/npm`.

**Dormice переворачивает этот подход:**  
Вы разворачиваете его на **собственном сервере (Self-Hosted)** как один легковесный демон со встроенной базой SQLite. Песочницы становятся **постоянными (персистентными)**, но при этом ничего не стоят в простое.

```text
┌────────────────────────────────────────────────────────────────────────┐
│                       ЖИЗНЕННЫЙ ЦИКЛ ПЕСОЧНИЦЫ DORMICE                 │
│                                                                        │
│   1. ACTIVE (Активна):                                                 │
│      Песочница исполняет код агента (память: 1 ГБ RAM)                 │
│                                │                                       │
│                                ▼ (Нет активности 60 секунд)            │
│   2. FROZEN (Заморожена):                                              │
│      Память сжимается до ~5 МБ RAM (пробуждение занимает 50 мс)        │
│                                │                                       │
│                                ▼ (Нет активности 1 час)                │
│   3. STOPPED (Остановлена):                                            │
│      RAM = 0 МБ. Состояние файлов лежит на локальном диске             │
│                                │                                       │
│                                ▼ (Нет активности 24 часа)              │
│   4. ARCHIVED (В архиве):                                              │
│      Упакована в ZSTD и сброшена в S3 / локальный архив                │
└────────────────────────────────────────────────────────────────────────┘
```

---

## 💎 2. Ключевые фичи

1. **Идемпотентный метод `acquireSandbox(userKey)`:**  
   Вся логика агента сводится к одному вызову. Если песочницы не было — она создается. Если спала в памяти — просыпается за 50 мс. Если была на диске — поднимается. Агент всегда возвращается в то же рабочее окружение.
2. **Полная совместимость с официальным SDK E2B:**  
   Если ваш код был написан под облачный сервис E2B, вы просто меняете базовый URL на свой сервер Dormice (`localhost:8080`) — и весь существующий код работает без изменений.
3. **Безопасность gVisor:**  
   Контейнеры изолируются не обычным Docker, а через песочницу Google gVisor (пользовательское ядро перехватывает и фильтрует системные вызовы Linux).
4. **Развертывание одной командой:**  
   Один бинарный демон, встроенный SQLite-реестр, отсутствие тяжелого Kubernetes.

---

## 🚀 3. Быстрый запуск

```bash
# Установка одной командой на чистый Ubuntu / Debian сервер:
curl -fsSL https://raw.githubusercontent.com/BitMiracle-AI/Dormice/main/deploy/install.sh | bash

# Использование через официальный E2B SDK в Python:
export E2B_API_URL="http://localhost:8080"
```

```python
from e2b import Sandbox

# Песочница поднимается на вашем личном сервере
sandbox = Sandbox()
execution = sandbox.commands.run("python3 -c 'print("Hello from self-hosted sandbox")'")
print(execution.stdout)
```

---
*Заметка сохранена: 2026-09-04 в /home/blackzeshi/Documents/Notes/02_agent_runtimes_and_harnesses/dormice.md*
