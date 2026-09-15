---
title: "LLMs from Scratch (Себастьян Рашка)"
repo: "https://github.com/rasbt/LLMs-from-scratch"
category: "01_llm_architecture_and_training"
tags: [llm, pytorch, transformers, from-scratch, education, deep-learning]
stars: "47.5k+"
date: 2026-08-24
---

# 🧠 Build a Large Language Model (From Scratch) — Sebastian Raschka

> **Ссылка на репозиторий:** [https://github.com/rasbt/LLMs-from-scratch](https://github.com/rasbt/LLMs-from-scratch)  
> **Автор:** Себастьян Рашка (Sebastian Raschka, Staff Research Engineer в Lightning AI, экс-профессор UW-Madison)  
> **Официальная книга:** *Build a Large Language Model (From Scratch)* (Manning Publications, ISBN 9781633437166)  
> **Звёзды GitHub:** 103,500+ ★  
> **Стек:** Python, PyTorch (чистый фреймворк без сторонних библиотек-обёрток), Jupyter Notebooks  
> **Требования к железу:** Обычный потребительский ноутбук (GPU опционален, код оптимизирован под CPU/MPS/CUDA)  

---

## 🎯 1. В чем главная ценность репозитория?

Большинство разработчиков используют LLM через API (OpenAI, Anthropic) или высокоуровневые библиотеки (`transformers`, `langchain`), воспринимая трансформеры как «черный ящик».

**LLMs-from-scratch** снимает эту магию:
* **0 сторонних высокоуровневых абстракций:** Каждый компонент — токенизатор, позиционное кодирование, Multi-Head Attention, блок трансформера, слой нормализации и функция потерь — пишется **на чистом PyTorch с нуля**.
* **Полный цикл разработки:** От загрузки сырого текста и предварительного обучения (Pre-training) до файнтюнинга инструкций (Instruction Tuning) и оценки сгенерированных ответов.
* **Доступность на потребительском железе:** Все базовые примеры и обучение мини-моделей выполняются за разумное время на обычном ноутбуке. Также есть код загрузки весов оригинального **GPT-2 (124M, 355M, 774M, 1558M)** от OpenAI для дообучения.

---

## 🗺 2. Ментальная модель архитектуры LLM

```text
[ Сырой текст ]
      │
      ▼
┌────────────────────────────────────────────────────────┐
│ Глава 2: Подготовка и токенизация                      │
│ • BPE Tokenizer (Byte-Pair Encoding)                   │
│ • Embedding Layer (Token + Positional Embeddings)      │
│ • Sliding Window DataLoader (Input-Target pairs)       │
└────────────────────────┬───────────────────────────────┘
                         │
                         ▼
┌────────────────────────────────────────────────────────┐
│ Глава 3: Механизмы внимания (Attention)                │
│ • Scaled Dot-Product Self-Attention                    │
│ • Causal Attention (маскирование будущих токенов)      │
│ • Multi-Head Attention (параллельные головы внимания)  │
└────────────────────────┬───────────────────────────────┘
                         │
                         ▼
┌────────────────────────────────────────────────────────┐
│ Глава 4: Архитектура GPT                               │
│ • Transformer Block (LayerNorm + MHA + GELU + MLP)     │
│ • Residual/Skip Connections (градиентные пробросы)     │
│ • Linear Head + Softmax (вероятности следующих токенов)│
└────────────────────────┬───────────────────────────────┘
                         │
                         ▼
┌────────────────────────────────────────────────────────┐
│ Глава 5: Предварительное обучение (Pretraining)        │
│ • Cross-Entropy Loss & Perplexity                      │
│ • Training Loop & Оптимизатор AdamW                    │
│ • Сэмплирование текста (Temperature, Top-K, Top-P)     │
└────────────────────────┬───────────────────────────────┘
                         │
       ┌─────────────────┴─────────────────┐
       ▼                                   ▼
┌──────────────────────────┐    ┌──────────────────────────┐
│ Глава 6: Классификация   │    │ Глава 7: Instruction SFT │
│ • Замена головы модели   │    │ • Формат Instruction/Ans │
│ • Fine-tuning под спам/  │    │ • Дообучение ассистента  │
│   сентимент-анализ       │    │ • Оценка через Ollama/LLM│
└──────────────────────────┘    └──────────────────────────┘
```

---

## 📖 3. Подробное содержание глав курса

### Глава 1: Understanding Large Language Models
* Высокоуровневый обзор концепций: авторегрессионные модели, этапы pre-training vs. fine-tuning, архитектура декодера трансформера (GPT-style) против энкодера (BERT-style).

### Глава 2: Working with Text Data
* Реализация собственного простого токенизатора.
* Использование промышленного алгоритма **BPE (Byte-Pair Encoding)** через `tiktoken`.
* Построение скользящего окна (`sliding window`) для генерации пар `(X, y)` для авторегрессионного обучения.
* Создание слоев матриц токен-эмбеддингов и позиционных эмбеддингов (`Token + Positional Embedding`).

### Глава 3: Coding Attention Mechanisms
* Математический вывод и пошаговая реализация формулы $Attention(Q, K, V) = softmax(\frac{QK^T}{\sqrt{d_k}})V$.
* **Causal Attention Masking:** зануление верхнего треугольника матрицы внимания, чтобы модель не подглядывала в будущие токены.
* **Dropout** в матрицах внимания.
* **Multi-Head Attention:** реализация объединения нескольких параллельных голов внимания в единый эффективный тензорный слой.

### Глава 4: Implementing a GPT Model from Scratch
* Сборка компонентов воедино:
  * **LayerNorm (Layer Normalization):** нормализация активаций по фичам.
  * **GELU Activation:** функция активации Gaussian Error Linear Unit.
  * **FeedForward Network (MLP):** двухслойная полносвязная сеть с расширением размерности в 4 раза.
  * **Shortcut / Residual Connections:** проброс градиентов в обход слоев.
* Класс `GPTModel` и генерация первых (пока случайных) токенов.

### Глава 5: Pretraining on Unlabeled Data
* Вычисление функции потерь `CrossEntropyLoss` над батчем последовательностей.
* Написание полноценного тренировочного цикла на чистом PyTorch.
* Загрузка весов оригинальной модели **GPT-2 (124M parameters)** от OpenAI в нашу собственную архитектуру.
* Алгоритмы декодирования: **Temperature Scaling**, **Top-K Sampling** для контроля креативности генерации.

### Глава 6: Finetuning for Text Classification
* Адаптация предобученной модели под прикладную задачу (например, классификация спама / отзывов).
* Замена финального проекционного слоя на классификационную голову (`Classification Head`).
* Заморозка весов трансформера и обучение только верхних слоев.

### Глава 7: Finetuning to Follow Instructions (Instruction Tuning)
* Превращение «генератора текста» в «полезного AI-ассистента».
* Подготовка датасетов в формате инструкций (Prompt-Response).
* Маскирование функции потерь (обучение градиентам только на ответе, а не на промпте).
* Автоматическая оценка качества модели с помощью локальных открытых LLM через **Ollama**.

---

## 🎁 4. Дополнительные модули и приложения (Appendices)

* **Appendix A: Introduction to PyTorch**  
  Базовый практический курс по тензорам PyTorch, автодифференцированию `autograd` и распределенному обучению на нескольких GPU (**DDP — Distributed Data Parallel**).
* **Appendix D: Adding Bells and Whistles to the Training Loop**  
  Инженерные техники стабилизации обучения: **Learning Rate Warmup**, **Cosine Annealing Scheduler**, **Gradient Clipping**.
* **Appendix E: Parameter-Efficient Finetuning with LoRA (Low-Rank Adaptation)**  
  Реализация метода LoRA с нуля: декомпозиция матриц весов $W_0 + B \cdot A$ для дообучения гигантских моделей при минимальных затратах VRAM.

---

## 🔮 5. Официальный сиквел: Build a Reasoning Model (From Scratch)

Себастьян Рашка выпустил продолжение книги:  
**[rasbt/reasoning-from-scratch](https://github.com/rasbt/reasoning-from-scratch)**

Книга и репозиторий посвящены реализации современных механизмов рассуждения (Reasoning Models à la DeepSeek R1 / OpenAI o1/o3):
* **Inference-time scaling** (масштабирование вычислений во время генерации).
* **Reinforcement Learning with Verifiable Rewards (RLVR)**.
* **Distillation** цепочек рассуждений (CoT — Chain of Thought).

---

## 🚀 6. Как запустить и экспериментировать локально

```bash
# 1. Клонирование репозитория
git clone --depth 1 https://github.com/rasbt/LLMs-from-scratch.git
cd LLMs-from-scratch

# 2. Создание виртуального окружения (через venv или uv)
python3 -m venv .venv
source .venv/bin/activate

# 3. Установка зависимостей
pip install -r setup/requirements.txt

# 4. Запуск Jupyter Notebook
jupyter lab
```

---
*Заметка сохранена: 2026-08-24 в /home/blackzeshi/Documents/Notes/LLMs-from-scratch.md*
