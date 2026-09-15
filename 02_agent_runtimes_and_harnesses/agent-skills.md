---
title: "Agent-Skills: Защищенный и верифицированный реестр навыков для кодинг-агентов (Tech Leads Club)"
repo: "https://github.com/tech-leads-club/agent-skills"
category: "02_agent_runtimes_and_harnesses"
tags: [agent-skills, skill-registry, antigravity, claude-code, cursor, supply-chain-security, verified-skills, mcp, spec-driven, typescript, snyk-agent-scan]
stars: "5.9k+"
date: 2026-09-14
---

# 🛡️ Agent-Skills: Защищенный и верифицированный реестр навыков для AI-агентов

> **Ссылка на репозиторий:** [https://github.com/tech-leads-club/agent-skills](https://github.com/tech-leads-club/agent-skills)  
> **Организация:** Tech Leads Club  
> **Официальный портал:** [https://tech-leads-club.github.io/agent-skills/](https://tech-leads-club.github.io/agent-skills/)  
> **Слоган:** *«The secure, validated skill registry for professional AI coding agents. Extend Antigravity, Claude Code, Cursor with absolute confidence.»*  
> **Звёзды GitHub:** 5,900+ ★  
> **Стек:** TypeScript, Node.js 22+, Nx Monorepo, Snyk Agent Scan  
> **Поддерживаемые агенты:** Antigravity (Tier 2), Claude Code (Tier 1), Cursor (Tier 1), Copilot, Codex, Windsurf, Cline  
> **Лицензия:** MIT  

---

## 🎯 1. В чем проблема и угроза открытых маркетплейсов навыков?

Агентные навыки (Agent Skills) на базе спецификации `SKILL.md` стали главным способом расширения возможностей современных кодинг-ассистентов. Однако бурный рост привел к серьезному кризису безопасности:
* **Критическая статистика Snyk Agent Scan:** Независимое исследование отчета безопасности выявило, что **более 13.4% публично распространяемых навыков содержат критические уязвимости**.
* **Скрытые инъекции и утечки (Prompt Leakage & Data Exfiltration):** Злоумышленники маскируют в промптах инструкции скрытно отправлять содержимое файлов `.env`, приватные SSH-ключи или токены окружения на внешние веб-серверы.
* **Supply-Chain атаки через утилиты:** Навыки часто требуют выполнения сторонних npm/pip пакетов или бинарников без проверки их цифровой подписи.

**Agent-Skills от Tech Leads Club** создан как защищенная, аутентифицированная и гарантированно безопасная библиотека навыков с эшелонированной защитой (Defense-in-Depth).

---

## 🔒 2. Архитектура безопасности: Defense-in-Depth

```text
┌─────────────────────────────────────────────────────────────┐
│                 Untrusted External Skill PR                 │
└──────────────────────────────┬──────────────────────────────┘
                               │
┌──────────────────────────────▼──────────────────────────────┐
│                  Continuous Security Pipeline               │
│                                                             │
│  1. 100% Pure Markdown & Source Only (Строгий запрет бинарников)
│  2. Snyk Agent Scan (Анализ инъекций, утечек и обходов песочниц)
│  3. Static Analysis & AST Linting (Nx CI/CD)                │
│  4. Human Expert Peer Review (Тройной ручной аудит)         │
│  5. Immutable Content Hashing & Cryptographic Lockfile      │
└──────────────────────────────┬──────────────────────────────┘
                               │ Verified & Signed Artifact
┌──────────────────────────────▼──────────────────────────────┐
│                    Hardened CLI Installer                   │
│                                                             │
│  • Path Traversal Guard: запрет выхода за пределы проекта   │
│  • Symlink Sanitization: предотвращение атак через ссылки   │
│  • Atomic Writes: исключение повреждения файлов при сбоях   │
│  • Comprehensive Audit Trail: фиксация всех внесенных правок│
└─────────────────────────────────────────────────────────────┘
```

---

## 🌟 3. Каталог ключевых проверенных навыков

| Навык | Категория | Ключевая функциональность |
| :--- | :---: | :--- |
| **`tlc-spec-driven`** | Разработка | Четырехфазное планирование проектов: *Specify $ightarrow$ Design $ightarrow$ Tasks $ightarrow$ Implement*. Формирует атомарные задачи с критериями приемки и ведет долговременную память между сессиями. |
| **`security-best-practices`** | Безопасность | Глубокий аудит кода под специфику языка и фреймворка. Обнаружение уязвимостей, генерация отчетов и автоматическое предложение исправлений класса secure-by-default. |
| **`playwright-skill`** | Автоматизация | Сквозная веб-автоматизация на базе Playwright: тестирование страниц, заполнение сложных форм, снятие скриншотов и валидация UX. |
| **`aws-advisor`** | Cloud | Экспертные консультации по архитектуре AWS, ревью политик IAM и практикам развертывания с валидацией через официальные AWS MCP инструменты. |
| **`figma`** | Дизайн | Извлечение дизайн-токенов и компонентов из Figma через MCP с последующей прямой трансляцией в чистый production-код на React/Tailwind. |

---

## 🚀 4. Быстрый запуск и управление

### Интерактивная установка навыков в проект
Инструмент поддерживает работу в один клик без глобальной установки:
```bash
# Интерактивный запуск установщика в текущем проекте
npx @tech-leads-club/agent-skills
```
Мастер автоматически определит установленные в вашей системе агенты (Antigravity, Claude Code, Cursor или Windsurf) и корректно сконфигурирует директории правил.

### Структура установленного навыка
```text
.agents/skills/
  development/
    tlc-spec-driven/
      SKILL.md          # Основной манифест с поведенческими правилами
      templates/        # Шаблоны проектных документов (SPEC.md, TASKS.md)
      references/       # Документация и паттерны, загружаемые по запросу
```

---

## 🔗 5. Синергия с другими компонентами базы знаний
* **Официальная поддержка Google Antigravity:** Проект официально классифицирует Antigravity как ключевую агентную платформу и обеспечивает 100% совместимость манифестов.
* **В паре со [SkillSpector](file:///home/blackzeshi/Documents/Notes/05_security_osint_and_guardrails/skillspector.md):** `SkillSpector` от NVIDIA служит локальным сканером для аудита любых неизвестных навыков, а `Agent-Skills` предоставляет централизованный источник уже проверенных и безопасных инструментов.
* **Связка с [Claude-Red](file:///home/blackzeshi/Documents/Notes/05_security_osint_and_guardrails/claude-red.md):** Показывает две стороны экосистемы навыков: специализированный Red Teaming для авторизованного тестирования против защищенного реестра для production-кодинга.
