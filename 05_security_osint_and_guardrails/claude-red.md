---
title: "Claude-Red: Кураторская библиотека наступательных навыков (Offensive Security Skills) для Claude"
repo: "https://github.com/SnailSploit/Claude-Red"
category: "05_security_osint_and_guardrails"
tags: [claude-skills, red-teaming, offensive-security, skill-md, prompt-engineering, pen-testing, exploit-development, edr-evasion, vulnerability-research, authorized-testing]
stars: "3.7k+"
date: 2026-09-13
---

# 🔴 Claude-Red: Кураторская библиотека наступательных навыков (Offensive Security Skills) для Claude

> **Ссылка на репозиторий:** [https://github.com/SnailSploit/Claude-Red](https://github.com/SnailSploit/Claude-Red)  
> **Автор / Организация:** SnailSploit  
> **Слоган:** *«Offensive security skills for Claude — drop-in SKILL.md files that turn Claude into a context-aware red team operator.»*  
> **Звёзды GitHub:** 3,700+ ★ (Топ-9 Trendshift Daily)  
> **Стек:** Markdown (`SKILL.md`), Shell, Claude Skills Framework  
> **Совместимость:** Claude Code, Claude Desktop, OpenAI Codex, Antigravity CLI  
> **Лицензия:** MIT  

---

## 🎯 1. В чем идея и проблематика?

При проведении санкционированного тестирования на проникновение (Penetration Testing), Red Teaming и исследовании защищенности ПО современные AI-ассистенты часто сталкиваются с двумя крайностями:
1. **Поверхностные ответы общего характера:** Обычный системный промпт не содержит глубокой предметной методологии (например, тонкостей обхода современных EDR-систем, фаззинга бинарных интерфейсов с AFL++ или нюансов эксплуатации протоколов Active Directory / ADCS). Модель скатывается в банальные рекомендации уровня «проверяйте входные данные».
2. **Перегрузка контекстного окна:** Если разработчик пытается загрузить сразу все методологии, утилиты и шпаргалки в один гигантский системный промпт, контекстное окно деградирует (Context Degradation), внимание модели рассеивается, а стоимость каждого вызова взлетает.

**Claude-Red** реализует модульный архитектурный подход на базе спецификации **Claude Skills**:
* Каждый вектор атаки или методология оформлены в виде отдельного структурированного файла `SKILL.md`.
* Навыки загружаются в контекст **динамически (On-Demand Activation)** только тогда, когда в диалоге возникает соответствующий триггер (например, обсуждение слепого SQLi активирует `offensive-sqli`, а анализ Kerberos-тикетов — навыки Active Directory).
* Агент сохраняет чистоту контекста для текущей задачи и получает экспертный уровень погружения без паразитных накладных расходов.

---

## 🗂️ 2. Каталог и таксономия (23 категории, 78+ скиллов)

Репозиторий охватывает практически все современные векторы тестирования защищенности, структурированные по директориям:

| Категория | Скиллы | Основной фокус и методология |
| :--- | :---: | :--- |
| **Web Applications** | 16 | OWASP Top 10, SQLi (error, blind, OOB), XSS (DOM, mXSS), SSRF (cloud metadata), SSTI, XXE, Deserialization, Race Conditions, Request Smuggling (CL.TE, TE.CL, H2 desync). |
| **Auth & Identity** | 2 | Эксплуатация уязвимостей JWT, атаки на протоколы OAuth 2.0 и OIDC. |
| **Active Directory** | 1 | Методологии атак на on-prem инфраструктуру Active Directory, Kerberoasting, AS-REP roasting. |
| **Wireless & IoT** | 15 | Беспроводные протоколы 802.11 (WPA2/3, Evil-Twin), Bluetooth Low Energy (BLE), Zigbee, LoRa, анализ прошивок и RTOS. |
| **Cloud & K8s** | 3 | Векторы атак в AWS, Azure, GCP; побег из контейнеров (Container Escape) и аудит кластеров Kubernetes. |
| **Exploit Development** | 6 | Анализ повреждения стека и кучи (Stack/Heap corruption), построение ROP-цепочек, обход ASLR/DEP, анализ сбоев (crash analysis). |
| **Fuzzing & Research** | 4 | Coverage-guided фаззинг с libFuzzer и AFL++, классификация уязвимостей и корневой анализ падений. |
| **Infrastructure & EDR** | 7 | Техники начального доступа (Initial Access), обход систем обнаружения EDR/XDR, Windows Internals, маскировка процессов. |
| **CI/CD & Supply Chain** | 4 | Эксплуатация пайплайнов GitHub Actions / GitLab CI, извлечение секретов, атаки типа Dependency Confusion. |
| **AI Security** | 1 | Анализ устойчивости LLM: Prompt Injection, Jailbreaking, отравление RAG-индекса (Data Poisoning). |
| **Utility & Reporting** | 2 | Чеклисты быстрого триажа и шаблоны профессиональных отчетов для баг-баунти и пентест-аудитов. |

---

## 🔬 3. Анатомия манифеста `SKILL.md`

Каждый навык в Claude-Red — это стандартизированный инженерный манифест со строгой внутренней иерархией:

```text
Skills/web/offensive-sqli/
├── SKILL.md            # Манифест с методологией, триггерами и чек-листом
└── references/         # Вспомогательные шпаргалки и специфичные особенности СУБД
```

### Ключевые секции манифеста:
1. **Frontmatter & Triggers:** Метаданные с ключевыми словами и шаблонами фраз, по которым рантайм агента автоматически активирует скилл.
2. **Reconnaissance & Fingerprinting:** Процедура идентификации технологии (версия СУБД, веб-сервера, WAF) без генерации шума.
3. **Escalation Decision Tree:** Дерево решений от обнаружения аномалии до подтверждения уязвимости.
4. **Edge Cases & Filter Bypasses:** Разбор нестандартных кодировок, двойных расширений, альтернативных синтаксисов и ограничений длины.
5. **Reporting & PoC Requirements:** Требования к оформлению доказательства концепции (PoC) с минимизацией деструктивного воздействия на целевую систему.

---

## 🛠️ 4. Варианты интеграции и сценарии использования

### Вариант A: Нативная интеграция с Claude Code
```bash
# Подключение отдельного навыка при запуске разовой сессии
cat Skills/web/offensive-sqli/SKILL.md | claude --system-file -

# Подключение всей категории инфраструктурного анализа
cat Skills/infrastructure-red-team/**/SKILL.md | claude --system-file -
```

### Вариант B: Выборочная установка через Git Sparse-Checkout
Если для проекта требуются только веб-навыки и аудит облачных сред, не нужно выкачивать весь 80-мегабайтный репозиторий:
```bash
git clone --filter=blob:none --sparse https://github.com/SnailSploit/claude-red
cd claude-red
git sparse-checkout set Skills/web Skills/cloud
```

### Вариант C: Интерактивный установщик
```bash
# Интерактивный мастер установки в профиль Claude
./install.sh --target ~/.claude/skills --category web
```

---

## ⚖️ 5. Этические рамки и синергия с Defensive-инструментами

> [!IMPORTANT]
> Репозиторий предназначен исключительно для авторизованных аудитов безопасности, программ Bug Bounty в рамках Scope, подготовки к CTF-соревнованиям и внутреннего Red Teaming.

В контексте нашей базы знаний `Claude-Red` образует мощный состязательный тандем с инструментами защиты:
* **Связка со [SkillSpector](file:///home/blackzeshi/Documents/Notes/05_security_osint_and_guardrails/skillspector.md):** Перед развертыванием сторонних скиллов их код анализируется сканером от NVIDIA на предмет скрытых бэкдоров и инъекций.
* **Связка с [TCB & Reference Monitor](file:///home/blackzeshi/Documents/Notes/05_security_osint_and_guardrails/tcb-agent-security.md):** Любые команды, генерируемые агентом под управлением `Claude-Red`, должны проходить через Reference Monitor с жестким разграничением прав и блокером вызовов.
