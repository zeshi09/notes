---
title: "Mister Download Manager (MDM): Clean-room open-source замена IDM на чистом Rust (14 крейтов, egui, BoringSSL, Torrents, MCP)"
repo: "https://github.com/anefzaoui/misterdownloadmanager"
category: "06_developer_tools_and_apps"
tags: [misterdownloadmanager, mdm, rust, egui, download-manager, idm-alternative, boringssl, bittorrent, yt-dlp, mcp, cross-platform, gpl3]
stars: "7.7k+"
date: 2026-11-13
---

# 🚀 Mister Download Manager (MDM): Модульный высокоскоростной менеджер загрузок на чистом Rust

> **Ссылка на репозиторий:** [https://github.com/anefzaoui/misterdownloadmanager](https://github.com/anefzaoui/misterdownloadmanager)  
> **Автор:** Ahmed Nefzaoui (`anefzaoui`)  
> **Категория:** `06_developer_tools_and_apps`  
> **Звёзды GitHub:** 7,740+ ★ (+918 ★ за сутки)  
> **Стек:** Rust (Edition 2024, Cargo workspace из 14 крейтов), `egui` (форк `storytold/egui`), BoringSSL, `librqbit`, `yt-dlp`, `ffmpeg`, `gallery-dl`, MCP  
> **Лицензия:** GPL-3.0

---

## 🎯 1. Суть проекта: Clean-room альтернатива Internet Download Manager

**Mister Download Manager (MDM)** воссоздаёт привычный UX классического IDM (категории, перехват из браузера, многопоточная сегментация, расписание, кнопка поверх видео), но написан **с нуля (clean-room)** на современном Rust без рекламы, триалов и закрытых бинарников, с нативной поддержкой **Windows, Linux** (Ubuntu/Debian/Fedora/Arch) и экспериментальными сборками под **macOS**.

---

## 🏗️ 2. Модульная архитектура (Cargo Workspace из 14 крейтов)

В отличие от монолитных GUI-приложений, MDM чётко разделён на независимые крейты и бинарники:

| Крейт | Роль в архитектуре |
| :--- | :--- |
| **`mdm-engine`** | Ядро загрузки: динамическая сегментация, ребалансировка потоков до последнего байта, докачка (RFC 9110/9112), лимиты скорости, TLS-стек через **BoringSSL** (браузерный TLS-отпечаток против антибот-блокировок) |
| **`mdm-app`** | Десктопный GUI на `egui` (10 тем, масштабирование до 200%, 86 языков с RTL, доступность Narrator/NVDA) + режим **`--headless`** для NAS/Docker/Unraid |
| **`mdm-cli`** | Headless CLI-клиент, совместимый с флагами командной строки IDM |
| **`mdm-mcp`** | **MCP-сервер** для AI-ассистентов (Claude, Cursor, VS Code — просмотр, добавление, пауза и удаление загрузок) |
| **`mdm-nmhost` / `mdm-ipc`** | Native Messaging Host и IPC для браузерного расширения (Firefox, Chrome, Edge, Brave, Opera, Vivaldi, Helium) с авто-возвратом загрузки браузеру, если MDM не запущен |
| **`mdm-remote`** | Встроенный HTTPS-сервер и веб-интерфейс для управления загрузками со смартфона в домашней сети |
| **`mdm-torrent`** | BitTorrent / magnet / sequential download / RSS через **`librqbit`** |
| **`mdm-tools`** | Интеграция с `yt-dlp` / `ffmpeg` (видео, плейлисты, субтитры) и `gallery-dl` (галереи изображений) |
| **`mdm-debrid`** | Поддержка Debrid-сервисов через официальные API (Real-Debrid, AllDebrid, Premiumize, TorBox) |
| **`mdm-extract` / `mdm-geo` / `mdm-crash`** | Автораспаковка архивов (`zip`, `tar`, `gz`, `xz`, а `7z`/`rar` через 7-Zip), определение страны сервера по локальной IP-базе, мониторинг крашей и зависаний |
| **`mdm-labserver`** | Локальный тестовый HTTP-сервер с инъекцией сбоев (fault injection) для воспроизводимых E2E-тестов и бенчмарков |

---

## 📊 3. Воспроизводимые бенчмарки против IDM 6.42

Автор включил в репозиторий собственный стенд (`crates/labserver` + `tools/bench`), тестирующий оба менеджера по умолчанию на 7 сетевых сценариях (7 прогонов, проверка значимости Mann-Whitney $p < 0.001$):

| Сценарий | MDM | IDM 6.42 | Ключевое отличие |
| :--- | :---: | :---: | :--- |
| **Большой файл (1 GB)** | **1.0 с** | 5.5 с | Динамическая ребалансировка сегментов до конца файла |
| **Малый файл / старт загрузки** | **мгновенно** | 3.1 с | Нулевая задержка инициализации |
| **Нестабильное соединение (shaky)** | **1.6 с** | 5.4 с | Быстрое переоткрытие подвисших диапазонов |
| **Сервер с лимитом 2 соединений** | **2 коннекта** | 480 коннектов | Уважение лимитов сервера вместо агрессивного переоткрытия |

---

## 🔒 4. Практичные сетевые и Dev-фичи

* **Привязка к VPN-интерфейсу (Kill Switch) + Encrypted DNS:** можно жёстко привязать все загрузки к конкретному сетевому адаптеру с мгновенной остановкой при разрыве VPN.
* **Скриншот- и i18n-автоматизация в CI:** `MDM_OFFSCREEN=1` (рендер всех окон без фокуса для авто-скриншотов и проверок в headless-среде), `MDM_FIT_AUDIT` (автоматическая проверка переполнения текста в интерфейсе на всех 86 языках), `node tools/extension/e2e.mjs` (E2E-тесты расширения в реальных Chrome/Brave/Edge/Firefox).

```bash
# Сборка всех 4 бинарников (app, cli, mcp, nmhost) из исходников (Rust 1.98+)
cargo build --release
cargo test

# Сборка без BoringSSL (если не установлены CMake / libclang / NASM)
cargo build -p mdm-app --no-default-features
```

---

## 💡 5. Главные инженерные выводы

1. **Эталонная культура Rust-разработки под десктоп:** встроенный `labserver` с fault injection, статистические бенчмарки, аудит вёрстки на 86 языках (`MDM_FIT_AUDIT`) и E2E-тесты браузерных расширений прямо в репозитории.
2. **BoringSSL в менеджере загрузок** — важное практическое решение: стандартные Rust TLS-библиотеки (rustls/native-tls) часто ловят 403/Cloudflare на CDN, тогда как BoringSSL имитирует TLS-отпечаток Chromium.
3. **Нативный MCP-сервер (`mdm-mcp`)** сразу встраивает десктопную утилиту в агентные пайплайны без костыльных CLI-обёрток.
