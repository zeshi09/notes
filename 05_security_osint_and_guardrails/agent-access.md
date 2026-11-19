---
title: "Bitwarden Agent Access: Открытый протокол, CLI (aac) и E2E-туннель выдачи секретов агентам без раскрытия Vault"
repo: "https://github.com/bitwarden/agent-access"
category: "05_security_osint_and_guardrails"
tags: [agent-access, bitwarden, secret-broker, tcb, noise-protocol, post-quantum, rust, cli, uniffi, wasm, mcp-security]
stars: "610+"
date: 2026-11-20
---

# 🔐 Bitwarden Agent Access: Защищённый E2E-туннель выдачи учётных данных AI-агентам

> **Ссылка на репозиторий:** [https://github.com/bitwarden/agent-access](https://github.com/bitwarden/agent-access)  
> **Организация:** Bitwarden (Open Source, *Early Preview* `v0.12.0`)  
> **Категория:** `05_security_osint_and_guardrails`  
> **Звёзды GitHub:** 618+ ★ (Trendshift #12, 2026-11-19)  
> **Стек:** Rust (Edition 2024, `1.85+`), Noise (`snow` `xchachapoly`, `clatter` ML-KEM + X25519, `ml-dsa`, `ed25519-dalek`), COSE/CBOR, WebSocket Relay, UniFFI (Python), WASM (JS)  
> **Лицензия:** Apache-2.0

---

## 🎯 1. В чём суть: выдавать агенту точечный секрет, не отдавая ключ от всего сейфа

Давать автономным агентам, CI-раннерам или удалённым воркерам мастер-пароль, `.env`-файл со всеми ключами или токен полного доступа к менеджеру паролей — критическая уязвимость. **Agent Access** — это открытый протокол, CLI-инструмент (`aac`) и Rust SDK от команды Bitwarden, которые поднимают **end-to-end шифрованный туннель** между удалённой средой и пользовательским менеджером паролей.

Причём для LLM-агентов авторы выделяют отдельный правильный паттерн: **не выгружать пароль в stdout/контекст модели**, а использовать **`aac run`** для прямой инъекции секрета в переменные окружения дочерней команды (`psql`, `deploy.sh`, `docker login`).

---

## 🏗️ 2. Архитектура туннеля и криптографический стек

```text
[Удалённый агент / CI / Sandbox]              [Машина пользователя + Vault]
  aac connect / aac run / SDK                    aac listen (--provider bitwarden)
  (ap-client / ap-uniffi / wasm)                 (bw CLI / внешний провайдер)
               │                                              ▲
               │  1. Noise NNpsk2 (XChaCha20-Poly1305 / PQ)   │
               │     + Pairing Token (PSK) или SHA-256 сверка │
               ▼                                              │
        ┌────────────────────────────────────────────────────────────┐
        │   Zero-Knowledge WebSocket Relay (`crates/ap-relay`)       │
        │   Пересылает шифротекст, не имея ключей и доступа к Vault  │
        └────────────────────────────────────────────────────────────┘
```

### Ключевые инженерные решения
1. **Протокол `ap-noise` (Noise `NNpsk2` + Multi-Device + Post-Quantum):**
   - Реализует паттерн **Noise `NNpsk2`** со свойствами **forward secrecy** и **break-in recovery**.
   - Поддерживает аутентификацию через **PSK (pairing token)** либо out-of-band сверку **SHA-256 handshake fingerprint** против MITM.
   - Включён экспериментальный постквантовый профиль (`experimental-post-quantum-crypto` через крейт **`clatter`** с гибридным обменом ключами **ML-KEM + X25519** и подписью **`ml-dsa`**).
2. **Credential Injection без засвета в контексте (`aac run`):**
   - `aac run` запрашивает запись по `--domain` или `--id`, передаёт нужные поля (`username`, `password`, `totp`, `uri`, `notes`, `domain`, `credential_id`) **строго через `env` дочернего процесса** (с `--env` или `--env-all` с префиксом `AAC_`), не записывая их на диск и не печатая в `stdout`.
3. **Кросс-языковые SDK и готовые интеграции:**
   - Workspace состоит из `ap-noise`, `ap-client`, `ap-cli` (`aac`), `ap-relay`, `ap-relay-client`, `ap-relay-protocol`, `ap-error`/`ap-error-macro` и **`ap-uniffi`**.
   - В `examples/` есть готовые примеры для **Python (UniFFI)**, **JS/WASM**, **GitHub Actions** (`reusable-psk-credential.yml`) и **OpenClaw `SKILL.md`**.

---

## 🚀 3. Быстрый старт (`aac` + Bitwarden CLI)

```bash
# На машине с разблокированным Bitwarden (или встроенный тестовый провайдер)
aac listen                 # требует bw CLI на PATH (/unlock, выдаёт pairing token)
aac listen --provider example

# На удалённой машине / в песочнице: привязка и инъекция в процесс (рекомендуемый режим для агентов)
aac connect --token <pairing-token> --output json
aac run --domain example.com --env DB_PASSWORD=password --env DB_USER=username -- psql
aac run --id <vault-item-id> --env-all -- deploy.sh
```

Использование через Python SDK (UniFFI):
```python
from agent_access import RemoteClient

client = RemoteClient("python-remote")
client.connect(token="ABC-DEF-GHI")
cred = client.request_credential("example.com")
client.close()
```

---

## 🔗 4. Синергия с базой знаний

* **Связка с [TCB & Reference Monitor](file:///home/blackzeshi/Documents/Notes/05_security_osint_and_guardrails/tcb-agent-security.md) и [Tool Broker Architecture](file:///home/blackzeshi/Documents/Notes/02_agent_runtimes_and_harnesses/tool-broker-architecture.md):** `Agent Access` — готовый open-source эталон **Credential Offloading / Secret Broker** на Rust: агент в песочнице не хранит постоянный сейф и даже при компрометации сессии не получает доступ ко всему Vault, а при использовании `aac run` секрет вообще не попадает в промпт.
* **Связка с [n8n Nod](file:///home/blackzeshi/Documents/Notes/02_agent_runtimes_and_harnesses/nod.md):** схожая идея изоляции секретов от контекста LLM (в Nod — локальный серверный Vault, в Bitwarden Agent Access — стандартизированный сетевой Noise-протокол от владельца паролей к удалённому воркеру/агенту).
