---
title: "AI Engineering from Scratch (Рохит Гумаре: 511 уроков, 20 фаз)"
repo: "https://github.com/blackzeshi/Git/ai-engineering-from-scratch"
category: "01_llm_architecture_and_training"
tags: [ai-engineering, roadmap, mcp, vllm, grpo, rag, agent-orchestration]
stars: "Local / 14k+"
date: 2026-08-26
---

# 🚀 AI Engineering from Scratch: Полная энциклопедия и руководство

> **Локальный путь:** [file:///home/blackzeshi/Git/ai-engineering-from-scratch](/home/blackzeshi/Git/ai-engineering-from-scratch)  
> **Ссылка на GitHub:** [https://github.com/rohitg00/ai-engineering-from-scratch](https://github.com/rohitg00/ai-engineering-from-scratch)  
> **Официальный сайт:** [https://aiengineeringfromscratch.com](https://aiengineeringfromscratch.com)  
> **Автор:** Рохит Гумаре (Rohit Ghumare, @rohitg00 — создатель [Agent Memory](https://github.com/rohitg00/agentmemory))  
> **Звёзды GitHub:** 49,300+ ★  
> **Объем:** **511 уроков**, **20 фаз**, **~329 часов практики**  
> **Языки реализации:** Python, TypeScript, Rust, Julia  
> **Лицензия:** MIT  

---

## 🎯 1. В чем главная ценность и масштабы курса?

> *«84% разработчиков уже используют AI-инструменты, но только 18% чувствуют себя готовыми создавать профессиональные AI-системы в продакшене.»*

**AI Engineering from Scratch** — это одна из самых монументальных и структурированных открытых программ обучения в мире по сквозной AI-инженерии. Она закрывает пропасть между поверхностным вызовом API через чат и глубоким пониманием того, как проектировать, обучать, оптимизировать, оркестрировать и безопасно развертывать AI-системы.

### Ключевые принципы курса:
1. **Каждый урок оставляет переиспользуемый артефакт:** работающий скрипт, промпт-шаблон, архитектурную схему, оптимизированный слой нейросети или CLI-утилиту.
2. **From Scratch (С нуля):** ключевые алгоритмы пишутся руками (Backpropagation, Attention, RAG, RLVR/GRPO, Agent Loop, MCP Server).
3. **Полиглотность:** основные алгоритмы на Python, высокопроизводительный инференс на Rust и C++, интерфейсы на TypeScript/React, научные вычисления на Julia.

---

## 🗺 2. Карта 20 фаз обучения (Phases 00–19)

```text
┌────────────────────────────────────────────────────────────────────────┐
│                      БЛОК 1: БАЗОВЫЙ ФУНДАМЕНТ                         │
│   Phase 00: Setup & Tooling (Linux, Docker, GPU, Profiling)            │
│   Phase 01: Math Foundations (Линейная алгебра, Анализ, Статистика)    │
│   Phase 02: ML Fundamentals (Регрессия, Деревья, SVM, Ансамбли)        │
│   Phase 03: Deep Learning Core (Backprop с нуля, PyTorch, CNN, LSTM)   │
└───────────────────────────────────┬────────────────────────────────────┘
                                    │
                                    ▼
┌────────────────────────────────────────────────────────────────────────┐
│                   БЛОК 2: МОДАЛЬНОСТИ И АРХИТЕКТУРЫ                    │
│   Phase 04: Computer Vision (ViT, Object Detection, Сегментация)       │
│   Phase 05: NLP Foundations to Advanced (Tokenizers, Embeddings)       │
│   Phase 06: Speech & Audio (Whisper, TTS, Audio Processing)            │
│   Phase 07: Transformers Deep Dive (Self-Attention, RoPE, KV Cache)    │
│   Phase 08: Generative AI (VAEs, GANs, Diffusion Models, Flow Matching)│
└───────────────────────────────────┬────────────────────────────────────┘
                                    │
                                    ▼
┌────────────────────────────────────────────────────────────────────────┐
│                   БЛОК 3: REASONING, RL И LLM                          │
│   Phase 09: Reinforcement Learning (PPO, DPO, GRPO, RLVR, RLHF)        │
│   Phase 10: LLMs from Scratch (Претрейн, Файнтюнинг, LoRA, QLoRA)      │
│   Phase 11: LLM Engineering (Advanced RAG, GraphRAG, Evals, Prompts)   │
│   Phase 12: Multimodal AI (VLM, Audio-LLMs, Embodied AI)               │
└───────────────────────────────────┬────────────────────────────────────┘
                                    │
                                    ▼
┌────────────────────────────────────────────────────────────────────────┐
│                   БЛОК 4: АГЕНТЫ, РОИ И ПРОТОКОЛЫ                      │
│   Phase 13: Tools & Protocols (Model Context Protocol / MCP, Tools)    │
│   Phase 14: Agent Engineering (ReAct, Память, Рефлексия, Планирование) │
│   Phase 15: Autonomous Systems (Долгие сессии, Sandboxing, State)      │
│   Phase 16: Multi-Agent & Swarms (Иерархии, Blackboard, Рои агентов)   │
└───────────────────────────────────┬────────────────────────────────────┘
                                    │
                                    ▼
┌────────────────────────────────────────────────────────────────────────┐
│             БЛОК 5: ПРОДАКШЕН, БЕЗОПАСНОСТЬ И ВЫПУСКНЫЕ ПРОЕКТЫ        │
│   Phase 17: Infrastructure & Production (vLLM, TensorRT-LLM, Квант.)   │
│   Phase 18: Ethics, Safety & Alignment (Guardrails, Jailbreak Defense) │
│   Phase 19: Capstone Projects (Полноценные сквозные приложения)        │
└────────────────────────────────────────────────────────────────────────┘
```

---

## 📚 3. Подробный разбор ключевых фаз

### 🧠 Фаза 07: Transformers Deep Dive
* Глубокий разбор математики матричного внимания: $QK^T / \sqrt{d_k}$.
* **Multi-Head Attention (MHA)**, **Multi-Query Attention (MQA)** и **Grouped-Query Attention (GQA)**.
* **FlashAttention (v1/v2/v3):** оптимизация работы с памятью GPU (SRAM vs HBM).
* **Positional Embeddings:** Sinusoidal, Learned, **RoPE (Rotary Position Embedding)**, ALiBi.
* **KV-Caching:** управление памятью генерации и оптимизация задержек Time-To-First-Token (TTFT).

### ⚡ Фаза 09: Reinforcement Learning & Reasoning (GRPO/DPO)
* От классического Q-learning до современных методов выравнивания LLM.
* **Direct Preference Optimization (DPO)** против PPO.
* **Group Relative Policy Optimization (GRPO)** — ключевой алгоритм моделей рассуждения в стиле **DeepSeek R1**.
* **RLVR (Reinforcement Learning with Verifiable Rewards)** — обучение с проверяемыми критериями истинности.

### 🏗 Фаза 11: LLM Engineering & GraphRAG
* **Advanced RAG:** гибридный поиск (BM25 + Dense Vectors), иерархический чанкинг, Re-ranking (Cross-Encoders).
* **GraphRAG:** извлечение триплетов сущностей, построение графов знаний, интеграция с Neo4j и Memgraph.
* **Evaluation & Benchmarks:** фреймворки Ragas, TruLens, DeepEval, синтетическая генерация тестовых датасетов.

### 🔌 Фаза 13: Tools & Model Context Protocol (MCP)
* Реализация серверов и клиентов **Model Context Protocol (MCP)** от Anthropic на Python и TypeScript.
* Динамическое обнаружение инструментов (Tool Discovery), передача ресурсов и управление контекстом.
* Построение шлюзов с ротацией ключей и защитой от перерасхода квот.

### 🤖 Фазы 14–16: Agent Engineering & Swarms
* **Архитектурные паттерны агентов:** ReAct (Reasoning + Acting), Plan-and-Solve, Reflexion, Tree-of-Thoughts.
* **Долговременная память:** краткосрочный буфер, векторная семантическая память, процедурная память навыков.
* **Мульти-агентные системы:** иерархические команды (Leader-Worker), архитектура общей доски (Blackboard), протоколы консенсуса в рое (Swarms).

### 🚀 Фаза 17: Infrastructure & Production Serving
* Высоконагруженный инференс через **vLLM** (PagedAttention), **TGI (Text Generation Inference)** и **TensorRT-LLM**.
* **Квантование моделей:** GPTQ, AWQ, GGUF/llama.cpp, FP8, bitsandbytes (INT8/INT4).
* Оптимизация пропускной способности (Continuous Batching, Speculative Decoding).
* Мониторинг и наблюдаемость: OpenTelemetry, Langfuse, Arize Phoenix, сбор метрик задержек (P95/P99).

---

## 🛠 4. Встроенные интерактивные скиллы (`skills/`)

В репозитории есть готовые AI-скиллы для работы с Claude Code, Antigravity, Cursor и Codex:

| Скилл | Назначение |
| :--- | :--- |
| **`find-your-level`** | Интерактивный тест для определения вашего текущего уровня знаний и подбора оптимальной точки старта. |
| **`start-learning`** | Автоматическая загрузка материалов, задач и чек-листов по выбранной фазе. |
| **`check-understanding`** | Генерация проверочных вопросов, код-ревью ваших решений и разбор ошибок. |
| **`learn-mcp`** | Специализированный интерактивный трек по созданию MCP-серверов. |
| **`learn-agent-skills`** | Обучение проектированию и стандартизации навыков для AI-агентов. |
| **`claude-certification`** | Подготовка к сертификациям по архитектуре Claude и агентным системам. |

---

## 💻 5. Как запустить и изучать локально

Репозиторий уже склонирован на вашей машине в директорию:  
📁 `/home/blackzeshi/Git/ai-engineering-from-scratch`

```bash
# 1. Переход в директорию проекта
cd /home/blackzeshi/Git/ai-engineering-from-scratch

# 2. Установка Python зависимостей (при необходимости)
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt

# 3. Запуск локального веб-сайта документации
cd site
node build.js
# Открытие локального интерфейса в браузере
```

---
*Заметка сохранена: 2026-08-26 в /home/blackzeshi/Documents/Notes/ai-engineering-from-scratch.md*
