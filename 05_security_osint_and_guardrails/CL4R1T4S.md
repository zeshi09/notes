---
title: "CL4R1T4S: База утекших системных промптов ведущих AI-моделей и агентов"
repo: "https://github.com/elder-plinius/CL4R1T4S"
category: "05_security_osint_and_guardrails"
tags: [system-prompts, transparency, red-teaming, prompt-engineering, guardrails, ai-security, jailbreak-analysis]
stars: "48.4k+"
date: 2026-09-02
---

# 🔓 CL4R1T4S: База утекших системных промптов ведущих AI-моделей и агентов

> **Ссылка на репозиторий:** [https://github.com/elder-plinius/CL4R1T4S](https://github.com/elder-plinius/CL4R1T4S)  
> **Автор:** Plinius the Elder (@elder-plinius)  
> **Слоган:** *«In order to trust the output, one must understand the input.»*  
> **Звёзды GitHub:** 48,400+ ★ (Лидер суточного чарта Trendshift)  
> **Сфера:** AI Transparency, Observability, System Prompts, Prompt Reverse-Engineering  
> **Лицензия:** MIT / Open Access  

---

## 🎯 1. В чем главная суть и зачем это нужно?

**CL4R1T4S** — это самый масштабный в мире открытый архив извлеченных, отреверсенных и утекших **официальных системных промптов (System Prompts)** практически всех ключевых коммерческих AI-моделей и кодинг-агентов.

Коммерческие AI-лаборатории (OpenAI, Anthropic, Google, xAI) определяют поведение моделей через гигантские скрытые системные инструкции (*Scaffolding Prompts*). Эти промпты определяют:
* **Границы отказов (Refusal Boundaries):** на какие темы модель обязана отвечать отказом или переводить тему.
* **Манеру и ролевую модель (Personas & Tone):** какой тон речи предписан модели.
* **Скрытые правила работы с тулами:** протоколы вызова поисковиков, интерпретатора кода, памяти и артефактов.
* **Политические и этические рамки (Framing):** заданные разработчиками по умолчанию.

> *«Если вы общаетесь с AI, не зная его системного промпта, вы общаетесь не с нейтральным интеллектом, а с куклой на веревочках».*

---

## 📂 2. Что внутри архива (Охваченные модели и агенты)

```text
┌────────────────────────────────────────────────────────────────────────┐
│                        АРХИВ СИСТЕМНЫХ ПРОМПТОВ                        │
│                                                                        │
│  🤖 ФЛАГМАНСКИЕ LLM:                                                   │
│  • OpenAI: ChatGPT (GPT-4o, o1-preview, o3-mini, GPT-5-sol)            │
│  • Anthropic: Claude (Claude 3.5 Sonnet, Claude 3.7 Sonnet)            │
│  • Google: Gemini (Gemini 1.5 Pro, Gemini 2.0 Flash)                   │
│  • xAI: Grok (Grok-2, Grok-3 System Rules)                             │
│  • Perplexity: Sonar, Pro Search prompts                               │
│                                                                        │
│  🛠 АВТОНОМНЫЕ АГЕНТЫ И AI-IDE:                                        │
│  • Cursor: System Prompt редактора, Composer, Shadow Workspace         │
│  • Windsurf / Cascade: промпты управления контекстом и терминалом     │
│  • Devin (Cognition) & Manus: агентные воркфлоу и планирование         │
│  • Replit Agent & Lovable: правила генерации full-stack проектов       │
└────────────────────────────────────────────────────────────────────────┘
```

---

## 💡 3. Практическая польза для инженера

1. **Изучение лучших практик промпт-дизайна:** Как ведущие команды формулируют запреты без галлюцинаций, как заставляют модель вызывать тулы в формате JSON/XML и как настраивают цепочки рассуждений (Chain-of-Thought).
2. **Аудит безопасности и Red Teaming:** Выявление слабых мест в чужих защитных барьерах для создания более надежных собственных агентных систем.
3. **Воспроизведение поведения в локальных моделях:** Возможность перенести структурированные инструкции коммерческих моделей на открытые Llama, Qwen и DeepSeek.

---
*Заметка сохранена: 2026-09-02 в /home/blackzeshi/Documents/Notes/05_security_osint_and_guardrails/CL4R1T4S.md*
