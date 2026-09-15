---
title: "Reasoning from Scratch (Себастьян Рашка: DeepSeek-R1, GRPO, RLVR)"
repo: "https://github.com/rasbt/reasoning-from-scratch"
category: "01_llm_architecture_and_training"
tags: [reasoning, deepseek-r1, grpo, rlvr, reinforcement-learning, inference-scaling]
stars: "18.2k+"
date: 2026-08-24
---

# 🧩 Build a Reasoning Model (From Scratch) — Sebastian Raschka

> **Ссылка на репозиторий:** [https://github.com/rasbt/reasoning-from-scratch](https://github.com/rasbt/reasoning-from-scratch)  
> **Автор:** Себастьян Рашка (Sebastian Raschka, Lightning AI)  
> **Официальная книга:** *Build a Reasoning Model (From Scratch)* (Manning Publications, ISBN 9781633434677)  
> **Статус:** Официальный сиквел к бестселлеру *Build a Large Language Model (From Scratch)*  
> **Стек:** Python, PyTorch, Jupyter Notebooks, Qwen3, GRPO, RL  
> **Ключевые темы:** Reasoning Models, DeepSeek-R1 архитектура, GRPO, Test-Time Compute, Inference-Time Scaling, Chain-of-Thought, Дистилляция  

---

## 🎯 1. Введение: Почему Reasoning — это революция в LLM?

### Проблема классических языковых моделей (System 1)
Обычные авторегрессионные LLM (GPT-4, Llama 3) генерируют каждый следующий токен с фиксированным числом вычислений, действуя по принципу **интуитивного мышления («System 1»)**:
* Если модели задать сложную математическую задачу или логическую головоломку, она вынуждена давать ответ «на лету», что приводит к грубым ошибкам и галлюцинациям.

### Что такое Reasoning Models («System 2»)?
Reasoning-модели (в стиле **DeepSeek R1**, **OpenAI o1 / o3**, **Qwen-QwQ**) тратят вычислительные ресурсы на «размышления» **во время инференса** (Inference-Time Scaling). Они генерируют скрытые цепочки рассуждений (`<think> ... </think>`), проверяют промежуточные шаги, исправляют собственные ошибки и только потом дают финальный ответ.

---

## 🗺 2. Ментальная модель книги и курса

```text
[ Предобученная базовая модель (Qwen3) ]
                   │
                   ▼
┌────────────────────────────────────────────────────────┐
│ ЭТАП 1: Inference-Time Scaling (без переобучения весов)│
│ • Chain-of-Thought (цепочки рассуждений)               │
│ • Best-of-N Sampling & Majority Voting                 │
│ • Self-Refinement & Iterative Critique (самокоррекция) │
└────────────────────────┬───────────────────────────────┘
                         │
                         ▼
┌────────────────────────────────────────────────────────┐
│ ЭТАП 2: Обучение с подкреплением (Reinforcement Learn) │
│ • Verifiable Rewards (награды за правильный ответ)     │
│ • GRPO (Group Relative Policy Optimization)            │
│ • Обучение рассуждениям в стиле DeepSeek-R1-Zero       │
└────────────────────────┬───────────────────────────────┘
                         │
                         ▼
┌────────────────────────────────────────────────────────┐
│ ЭТАП 3: Дистилляция (Distillation)                     │
│ • Перенос цепочек рассуждений в компактные модели      │
│ • Эффективный инференс на потребительских устройствах  │
└────────────────────────────────────────────────────────┘
```

---

## 📖 3. Поглавная структура курса (Chapters 1–8)

### Глава 1: Understanding Reasoning Models
* Разбор фундаментальных отличий между генерацией текста и логическим рассуждением.
* Эволюция подходов: от промптинга (CoT, Tree-of-Thoughts) к архитектурному масштабированию времени вычислений (Test-Time Compute).

### Глава 2: Generating Text with a Pre-trained LLM
* Подготовка базовой среды и загрузка весов открытой модели **Qwen3**.
* Организация цикла генерации токенов на чистом PyTorch.

### Глава 3: Evaluating Reasoning Models
* Метрики и бенчмарки для строгой оценки логики и математики: **GSM8K**, **MATH**, **ARC-Challenge**, **AIME**.
* Оценка точности по метрикам **Pass@1** и **Pass@k**.

### Глава 4: Improving Reasoning with Inference-Time Scaling
* Методы параллельного сэмплирования нескольких путей решения без изменения весов:
  * **Majority Voting (Self-Consistency):** выбор ответа большинством голосов.
  * **Best-of-N:** генерация $N$ вариантов с выбором лучшего через Reward Model или верификатор.

### Глава 5: Inference-Time Scaling via Self-Refinement
* Архитектура **самокоррекции (Self-Correction / Critique)**:
* Модель сначала генерирует черновик решения, затем отдельным проходом критикует свои выкладки, находит логические нестыковки и переписывает решение начисто.

### Глава 6: Training Reasoning Models with Reinforcement Learning
* Полноценная реализация RL-пайплайна для обучения рассуждениям:
* **Verifiable Reward Functions (RLVR):** детерминированная проверка правильности математического ответа или прохождения юнит-тестов в коде (вместо субъективной Human Feedback).
* Обучение модели генерировать длинные размышления через штрафы и поощрения.

### Глава 7: Implementing GRPO (Group Relative Policy Optimization)
* Пошаговая реализация алгоритма **GRPO** (ключевой алгоритм DeepSeek R1) с нуля на PyTorch:
* **В чем прорыв GRPO:** в отличие от классического PPO, GRPO **не требует отдельной тяжелой модели-критика (Value Network / Critic Model)**, что снижает потребление видеопамяти на 50% и упрощает обучение.
* Расчет преимуществ (advantages) на основе относительного ранжирования группы сгенерированных ответов.

### Глава 8: Distilling Reasoning Models
* Как перенести способность рассуждать из гигантской модели (например, 70B/671B) в компактную (например, 1.5B/7B/8B).
* Тюнинг по шаблону SFT на синтетических рассуждениях DeepSeek R1 / QwQ.

---

## 🎁 4. Приложения и инженерные техники (Appendices)

* **Appendix C: Qwen3 LLM Source Code** — полный исходный код архитектуры модели Qwen3 на PyTorch.
* **Appendix D: Using Larger LLMs** — техники работы с крупными моделями на доступных GPU.
* **Appendix E: Batching & High-Throughput Execution** — оптимизация батчинга при параллельной генерации деревьев рассуждений.
* **Appendix F: Common Approaches to LLM Evaluation** — методология тестирования LLM против датасетов-ловушек.
* **Appendix G: Building a Chat Interface** — создание интерактивного чат-интерфейса с раскрывающимися блоками `<think>...</think>`.

---

## ⚖️ 5. Сравнение двух книг Себастьяна Рашки

| Характеристика | *Build an LLM (From Scratch)* | *Build a Reasoning Model (From Scratch)* |
| :--- | :--- | :--- |
| **Основная цель** | Создать базовую GPT-2/3 модель с нуля | Научить модель логике, рассуждениям и самокоррекции |
| **Фокус разработки** | Архитектура: Attention, Transformer, SFT | Алгоритмы: **GRPO, RL, Inference Scaling, CoT** |
| **Базовая модель** | Обучение собственной мини-модели с нуля | Предобученная открытая модель (**Qwen3**) |
| **Аналог в индустрии** | GPT-2 / GPT-3.5 / Llama 3 | **DeepSeek-R1 / OpenAI o1 / Qwen-QwQ** |

---

## 🚀 6. Как запустить и изучать локально

```bash
# 1. Клонирование репозитория
git clone --depth 1 https://github.com/rasbt/reasoning-from-scratch.git
cd reasoning-from-scratch

# 2. Создание виртуального окружения
python3 -m venv .venv
source .venv/bin/activate

# 3. Установка зависимостей
pip install -r setup/requirements.txt

# 4. Запуск Jupyter Lab
jupyter lab
```

---
*Заметка сохранена: 2026-08-24 в /home/blackzeshi/Documents/Notes/reasoning-from-scratch.md*
