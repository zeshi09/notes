---
title: "Fastpotify: Нативный и молниеносный клиент Spotify на Rust"
repo: "https://github.com/crmne/fastpotify"
category: "06_developer_tools_and_apps"
tags: [rust, desktop-app, spotify, egui, librespot, audio-player]
stars: "1.3k+"
date: 2026-09-01
---

# 🎵 Fastpotify: Нативный и молниеносный клиент Spotify на Rust

> **Ссылка на репозиторий:** [https://github.com/crmne/fastpotify](https://github.com/crmne/fastpotify)  
> **Официальный сайт:** [https://fastpotify.rocks](https://fastpotify.rocks)  
> **Автор:** Carmine (@crmne)  
> **Звёзды GitHub:** 1,300+ ★  
> **Стек:** 100% чистый Rust, egui, librespot, rodio  
> **Платформы:** Linux, macOS, Windows  
> **Лицензия:** GPL-3.0  

---

## 🎯 1. В чем идея проекта?

Официальный десктопный клиент Spotify построен на базе Electron/Chromium: он потребляет от **600 МБ до 1.5 ГБ оперативной памяти**, запускается по несколько секунд и нагружает процессор фоновыми веб-процессами.

**Fastpotify** — это нативный клиент Spotify с графическим интерфейсом на фреймворке **egui**, написанный полностью на **Rust** с использованием открытой библиотеки **librespot**.

```text
| Характеристика | Официальный Spotify Desktop | Fastpotify (Rust) |
| :--- | :--- | :--- |
| **Стек** | Electron / CEF / Chromium | Чистый Rust + egui |
| **Потребление RAM** | 600 МБ – 1.5 ГБ | **100 – 250 МБ** |
| **Время запуска** | 3–6 секунд | **< 0.5 секунды** |
| **Движок браузера** | Полный Chromium | **Отсутствует (Чистый GPU-рендеринг)** |
| **Управление устройствами** | Spotify Connect | **Полная поддержка Spotify Connect** |
| **Качество звука** | До 320 kbps (Ogg Vorbis) | **До 320 kbps + Gapless Playback** |
```

---

## 💎 2. Ключевые возможности

1. **Spotify Connect:** Компьютер с Fastpotify отображается как устройство Spotify Connect в мобильном приложении на телефоне — можно переключать треки с любого гаджета.
2. **Gapless Playback (Бесшовное воспроизведение):** Плавный переход между треками альбома без пауз и задержек.
3. **Локальный ауди Fast-кэш:** Кэширование треков на диске для мгновенного повторного воспроизведения без расхода трафика.
4. **Нормализация громкости:** Встроенная поддержка ReplayGain / EBU R128.

> *Примечание:* Для воспроизведения аудио требуется учетная запись Spotify Premium (ограничение протокола librespot). Бесплатные аккаунты могут просматривать треки, альбомы и тексты.

---

## 🚀 3. Быстрый запуск

```bash
# Сборка и запуск на Linux / macOS / Windows
git clone https://github.com/crmne/fastpotify.git
cd fastpotify
cargo run --release
```

---
*Заметка сохранена: 2026-09-01 в /home/blackzeshi/Documents/Notes/fastpotify.md*