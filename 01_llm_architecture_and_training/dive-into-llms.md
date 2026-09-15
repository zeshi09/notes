---
title: "Dive into LLMs (动手学大模型): Практический курс инженерии больших языковых моделей"
repo: "https://github.com/Lordog/dive-into-llms"
category: "01_llm_architecture_and_training"
tags: [llm, transformers, pretraining, sft, lora, rlhf, dpo, quantization, vllm, deep-learning, jupyter]
stars: "51.3k+"
date: 2026-09-02
---

# 📚 Dive into LLMs: Практический курс инженерии больших языковых моделей

> **Ссылка на репозиторий:** [https://github.com/Lordog/dive-into-llms](https://github.com/Lordog/dive-into-llms)  
> **Название:** 《动手学大模型 Dive into LLMs》  
> **Автор:** Lordog & Open Source Community  
> **Звёзды GitHub:** 51,300+ ★  
> **Формат:** Интерактивные Jupyter Notebooks, чистый PyTorch, Hugging Face, vLLM  
> **Лицензия:** Apache-2.0  

---

## 🎯 1. Концепция и отличие от других курсов

Подобно легендарному курсу *Dive into Deep Learning (D2L)*, **Dive into LLMs** ставит во главу угла принцип: **«Пойми через реализацию кода собственными руками»**.

Вместо абстрактной теории курс ведет инженера пошагово через все стадии жизненного цикла современных LLM: от перемножения матриц в блоке внимания до распределенного инференса с RadixAttention и квантования в 4 бита.

---

## 🗺 2. Программа курса и модули

```text
┌────────────────────────────────────────────────────────────────────────┐
│                        ПРОГРАММА DIVE INTO LLMS                        │
│                                                                        │
│  МОДУЛЬ 1: АРХИТЕКТУРА И ТОКЕНИЗАЦИЯ                                   │
│  • Реализация BPE и SentencePiece токенизаторов с нуля                 │
│  • Multi-Head Attention, Grouped-Query Attention (GQA), FlashAttention │
│  • Позиционные эмбеддинги: RoPE (Rotary Position Embeddings), YaRN     │
│  • Нормализации: RMSNorm, SwiGLU функции активации                     │
│                                                                        │
│  МОДУЛЬ 2: ПРЕДВАРИТЕЛЬНОЕ ОБУЧЕНИЕ (Pre-training)                     │
│  • Подготовка терабайтных корпусов данных, дедупликация (MinHash)      │
│  • Распределенное обучение: Data Parallel, Tensor Parallel, ZeRO (FSDP)│
│                                                                        │
│  МОДУЛЬ 3: ДООБУЧЕНИЕ И ВЫРАВНИВАНИЕ (SFT & Alignment)                │
│  • Supervised Fine-Tuning на диалогах (ChatML шаблоны)                 │
│  • Параметрически эффективное дообучение: LoRA, QLoRA, DoRA            │
│  • Обучение с подкреплением: RLHF (PPO), DPO (Direct Preference), GRPO │
│                                                                        │
│  МОДУЛЬ 4: СКОРОСТНОЙ ИНФЕРЕНС И РАЗВЕРТЫВАНИЕ                         │
│  • Оптимизация KV-кэша, PagedAttention, vLLM, SGLang                   │
│  • Квантование: GPTQ, AWQ, BitsAndBytes (4-bit/8-bit), GGUF            │
└────────────────────────────────────────────────────────────────────────┘
```

---

## 🚀 3. Как запустить локально?

```bash
# Клонирование репозитория
git clone https://github.com/Lordog/dive-into-llms.git
cd dive-into-llms

# Установка окружения
pip install -r requirements.txt

# Запуск интерактивных блокнотов
jupyter lab
```

---
*Заметка сохранена: 2026-09-02 в /home/blackzeshi/Documents/Notes/01_llm_architecture_and_training/dive-into-llms.md*
