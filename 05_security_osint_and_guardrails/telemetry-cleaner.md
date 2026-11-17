---
title: "TelemetryCleaner: Удаление скрытых системных модулей телеметрии в Android через Shizuku (Binder + app_process) без Root"
repo: "https://github.com/Eynnzerr/TelemetryCleaner"
category: "05_security_osint_and_guardrails"
tags: [telemetry-cleaner, android-security, privacy, shizuku, binder, systemhelper, debloat, kotlin, no-root]
stars: "940+"
date: 2026-11-16
---

# 📱 TelemetryCleaner: Очистка предустановленных модулей телеметрии на Android без Root

> **Ссылка на репозиторий:** [https://github.com/Eynnzerr/TelemetryCleaner](https://github.com/Eynnzerr/TelemetryCleaner)  
> **Категория:** `05_security_osint_and_guardrails`  
> **Звёзды GitHub:** 947+ ★ (Trendshift #11, 2026-11-16)  
> **Стек:** Kotlin, Android 10+ (Shizuku, Binder IPC, `app_process` / `IPackageManager`)  
> **Лицензия:** MIT

---

## 🎯 1. В чём проблема: «невидимые» операторские пакеты в прошивках

Во многих китайских прошивках Android (ColorOS/OPPO, HyperOS/MIUI, HarmonyOS/EMUI, OriginOS и др.) в систему вшиты компоненты вроде **`SystemHelper`** и **`RegService`** для регистрации устройств у операторов (China Telecom, China Mobile, China Unicom).

По данным исследования **WiSec 2023** и собственного реверс-анализа автора на реальном OPPO (`docs/systemhelper-analysis.md`):
- эти модули **не имеют иконки на рабочем столе** и работают в фоне;
- стандартный интерфейс Android **не даёт отключить им разрешения или удалить их**;
- на устройстве автора наблюдался сбор геолокации, идентификаторов устройства и SIM, списка установленных приложений и поприложенческой статистики трафика с отправкой в облако.

---

## 🏗️ 2. Как работает удаление без Root (`Shizuku` + обход ограничений ROM)

Обычные деблоатеры вызывают команду `adb shell pm uninstall`, но часть прошивок жёстко блокирует CLI-обёртку `pm` для системных пакетов. В TelemetryCleaner реализована **двухступенчатая схема через shell-права Shizuku**:

```text
Android 10+ (ADB / Wireless Debugging Android 11+) ──► Shizuku (uid=2000 shell)
   │
   ├── 1. Основной путь (`PackageBinder.kt`):
   │      Прямые Binder IPC-вызовы к системному PackageManagerService
   │      в обход ограничений CLI-команды `pm`.
   │
   └── 2. Fallback при отказе ROM (`PackageFallback.kt`):
          Если прошивка отвечает `Failure [only root can delete system app for a particular user]`,
          запускается `app_process` от имени shell с вызовом скрытого
          `IPackageManager.deletePackageAsUser(...)`.
```

### Ключевые возможности приложения
* **Работа по пространствам (user/work profiles):** отображает статус установки и выданные разрешения по каждому профилю отдельно; при удалении чистит данные пакета в выбранном пространстве, а восстановление возможно из сохранённого системного APK.
* **Фоновая автоочистка (выключена по умолчанию):** может периодически проверять выбранные пространства на возвращение пакетов из списка (например, после OTA-обновления) и заново их чистить.
* **Ограничения и заморозка:** для части устройств **vivo** удаление компонентов за пределами `SystemHelper` пока не поддерживается (известен побочный эффект потери записи звонков после удаления Device Management на vivo) — для них добавлена стратегия **заморозки (freeze)** как fallback.

---

## 📋 3. Встроенный каталог проверяемых пакетов

| Производитель / Оператор | Пакет | Статус проверки |
| :--- | :--- | :--- |
| **Кросс-вендор (China Unicom)** | `com.mobiletools.systemhelper` | Проверено |
| **OPPO / OnePlus / realme (Telecom / Mobile)** | `com.oppo.ctautoregist`, `com.coloros.regservice` | Проверено |
| **Xiaomi / Redmi / POCO (Telecom / Mobile)** | `com.xiaomi.registration`, `com.miui.dmregservice` | Проверено |
| **Huawei / старые Honor** | `com.huawei.android.UEInfoCheck`, `AutoRegSms`, `regservice` | Проверено |
| **vivo** | `com.vivo.devicereg` | Частично (есть freeze) |
| **Honor / Meizu / Nubia** | `com.hihonor.*`, `com.meizu.regservice`, `cn.nubia.register` | В каталоге (не проверено) |

---

## 🔗 4. Синергия с базой знаний

* **Связка с [APK-Reverse](file:///home/blackzeshi/Documents/Notes/05_security_osint_and_guardrails/apk-reverse.md):** отличная связка для анализа мобильных прошивок — через `apk-reverse` разбираются системные APK и их трекинг-эндпоинты, а паттерн `Binder` + `app_process` из `TelemetryCleaner` показывает, как системно управлять такими пакетами без Root.
* **Связка с [SilentSniffer](file:///home/blackzeshi/Documents/Notes/05_security_osint_and_guardrails/silentsniffer.md):** продолжение темы аудита скрытой телеметрии и сбора фингерпринтов устройства (там — со стороны Web/Browser API, здесь — на уровне ОС Android).
