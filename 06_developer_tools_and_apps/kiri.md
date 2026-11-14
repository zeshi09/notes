---
title: "Kiri: Сверхлёгкий контейнерный рантайм на Rust с запуском за 2.5 мс для macOS, Windows и Linux"
repo: "https://github.com/libracoder/kiri"
category: "06_developer_tools_and_apps"
tags: [kiri, rust, containers, docker, oci, virtualization, kubernetes, vsock, clone3, linux-kernel, cross-platform]
stars: "3.1k+"
date: 2026-11-14
---

# ⚡ Kiri: Сверхлёгкий контейнерный рантайм на Rust (замена Docker Desktop и OrbStack)

> **Ссылка на репозиторий:** [https://github.com/libracoder/kiri](https://github.com/libracoder/kiri)  
> **Официальный сайт:** [https://runkiri.com](https://runkiri.com)  
> **Категория:** `06_developer_tools_and_apps`  
> **Звёзды GitHub:** 3,155+ ★ (Trendshift Top #4, 2026-11-14)  
> **Стек:** Rust (Edition 2024), `objc2-virtualization` (Apple Virtualization.framework), WSL 2 (`kiri-win`), custom Linux kernel (10 MB), `vsock`, `clone3`, `rtnetlink`, `nf_tables`, `virtiofs`  
> **Лицензия:** Apache-2.0

---

## 🎯 1. В чём суть: почему Kiri в 80 раз быстрее Docker Desktop

**Kiri** (от игбо *ntakịrị* — «маленький») — компактная замена Docker Desktop и OrbStack, написанная на Rust. Демон общается с обычными `docker`, `docker compose`, `buildx` и `kubectl` по стандартному **Docker Engine API**, но внутри гостевой Linux-VM (или напрямую на ядре в Linux) **полностью выкинуты `dockerd`, `containerd-shim` и `runc`**.

Вместо цепочки прослоек гостевой агент PID 1 поднимает контейнер одним системным вызовом `clone3(CLONE_INTO_CGROUP)` напрямую в нужные namespaces и cgroup.

### Замеры производительности (`alpine` + `true` + `--rm`, медиана 30 прогонов)

| Рантайм | Docker Engine API | `docker` CLI | Ресурсы в простое |
| :--- | :---: | :---: | :--- |
| **Kiri** | **2.55 ms** | **14.2 ms** | VM засыпает через 60 с; демон **~15 MB RAM**, пробуждение **~0.15 s** |
| **Docker Desktop** | 213 ms | 243 ms | Тяжёлый фоновый стек (`dockerd` + `containerd` + VM) |
| **OrbStack** | 380 ms | 442 ms | — |

---

## 🏗️ 2. Архитектура и модули Workspace

```text
docker CLI ──┐
compose ─────┼─► ~/.kiri/run/docker.sock ─► kiri daemon (Rust, ~15 MB)
buildx ──────┤      (Docker Engine API)           │
kiri UI ─────┘                                  vsock (kiri-proto, no_std, zero-alloc)
                                                  ▼
                                    Guest VM (custom 10 MB Linux kernel)
                                      └─► kiri-init (PID 1, ~900 KB static Rust)
                                            ├─ один poll()-цикл (события, DNS, DHCP, порты)
                                            ├─ clone3(CLONE_INTO_CGROUP) -> overlayfs + pivot_root
                                            ├─ rtnetlink + nf_tables (сеть вручную без iptables/CNI)
                                            └─ fork() для docker cp, чтобы не блокировать PID 1
```

### Устройство крейтов и ключевые инженерные решения

| Компонент | Роль |
| :--- | :--- |
| **`crates/kiri`** | Основной бинарник: демон, Docker Engine API, CLI, нативный UI (38 языков, включая русский) и `kiri bench`. |
| **`crates/kiri-vmm`** | Загрузка и управление VM на macOS через `Virtualization.framework` (`objc2-virtualization`). |
| **`crates/kiri-init`** | Статический Rust-бинарник (~900 KB) в роли **PID 1** внутри VM: единый `poll()`-цикл, сбор зомби-процессов, релей портов, встроенные DNS/DHCP и запуск контейнеров. |
| **`crates/kiri-proto`** | Протокол хост ↔ гость поверх `vsock`: `#![no_std]`, **без аллокаций на сообщение**. |
| **`crates/kiri-image`** | Парсинг ссылок на образы, registry-клиент (`pull`/`push` с `docker login` на стороне хоста), blob-хранилище, стриминг слоёв в гостя. |
| **`crates/kiri-win`** | Интеграция для Windows 10/11 (x86-64 и Arm) поверх WSL 2. |
| **`guest/kernel/`** | Минимальное ядро (~10 MB, база `allnoconfig`) с патчами: ускорение reset `virtio-pci` до микросекунд, GSO для крупного TCP на хост, корректные права FUSE и фикс GRO. |

---

## ⚙️ 3. Функциональность и безопасность

* **Совместимость с Docker / Compose / BuildKit:** поддержка `run`, `exec`, `logs`, `cp`, `commit`, Compose-проектов, BuildKit через `buildx`, а на Apple Silicon — запуск `amd64`-образов и шагов сборки через **Rosetta** (`virtiofs` + `binfmt_misc`).
* **Сеть и локальные домены:** пользовательские сети с DNS, IPv4/IPv6 (`fd00::/8`), локальные домены `http://<name>.kiri.local` / `*.kiri.localhost` и авто-HTTPS с собственным CA в `~/.kiri/tls` (ограниченным через name constraints строго на `*.kiri.local` и `*.kiri.localhost`).
* **Kubernetes и Linux-машины:** `kiri k8s start` (single-node Kubernetes с контекстом `kiri`), `kiri machine create` для полноценных Linux-окружений, `kiri import` для миграции образов/томов из Docker Desktop или OrbStack.
* **USB-проброс (beta):** передача последовательных адаптеров и отладочных плат внутрь контейнеров на Mac, Windows и Linux с переподключением после сна.
* **Жёсткая изоляция хоста:** даже при `--privileged` и `--security-opt seccomp=unconfined` внутри контейнера заблокированы `vsock`-сокеты (канал к хосту) и `io_uring`. В самом Rust-коде включены `#![deny(unsafe_op_in_unsafe_fn)]` и `panic = "abort"`.

---

## 🚀 4. Быстрый старт

```bash
# Проверка через стандартный docker CLI (после установки Kiri)
docker --context kiri run --rm alpine echo hello
docker --context kiri compose up -d

# Или напрямую через CLI Kiri
kiri run --rm alpine echo hello
kiri k8s start
kiri machine create dev --distro ubuntu && kiri machine shell dev
kiri import
kiri bench
```

---

## 🔗 5. Синергия с базой знаний

* **Связка с [ArcBox](file:///home/blackzeshi/Documents/Notes/02_agent_runtimes_and_harnesses/arcbox.md) и [ZeroBoot](file:///home/blackzeshi/Documents/Notes/02_agent_runtimes_and_harnesses/zeroboot.md):** показывает тот же класс Rust-подходов к минимальному VMM и сверхбыстрому старту без тяжёлых OCI-прослоек (`runc`/`containerd`), но ориентированный не только на песочницы агентов, а на полноценный ежедневный Docker/K8s workflow.
* **Связка с [Linux Kernel & Container Hardening](file:///home/blackzeshi/Documents/Notes/05_security_osint_and_guardrails/linux-kernel-and-container-hardening.md):** отличный практический пример ручной работы с `clone3`, `CLONE_INTO_CGROUP`, `pivot_root`, `rtnetlink`, `nf_tables` и фильтрацией `io_uring`/`vsock`.
