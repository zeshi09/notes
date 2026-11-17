---
title: "Google PaperOrchestra: Мультиагентный конвейер превращения сырых логов и идей в готовую LaTeX-статью"
repo: "https://github.com/google-research/paper-orchestra"
category: "04_scientific_research_and_discovery"
tags: [paper-orchestra, google-research, scientific-writing, multi-agent, latex, literature-review, plotting, autoraters, python, arxiv]
stars: "820+"
date: 2026-11-16
---

# 🎻 Google PaperOrchestra: Мультиагентный фреймворк автоматического написания AI-статей

> **Ссылка на репозиторий:** [https://github.com/google-research/paper-orchestra](https://github.com/google-research/paper-orchestra)  
> **Страница проекта:** [https://yiwen-song.github.io/paper_orchestra/](https://yiwen-song.github.io/paper_orchestra/)  
> **Статья:** [arXiv:2604.05018](https://arxiv.org/abs/2604.05018) *(Google Cloud AI Research)*  
> **Категория:** `04_scientific_research_and_discovery`  
> **Звёзды GitHub:** 821+ ★ (Trendshift #22, 2026-11-16)  
> **Стек:** Python 3.11, Gemini / Vertex AI / OpenAI, Semantic Scholar API, LaTeX (CVPR 2025 / ICLR 2025), Streamlit  
> **Лицензия:** Apache-2.0

---

## 🎯 1. В чём суть: от неструктурированных заметок и логов к готовому PDF

**PaperOrchestra** закрывает разрыв между сырыми материалами исследователя (текстовые идеи, таблицы и логи экспериментов) и отформатированной научной публикацией в LaTeX под требования конкретной конференции. Вместо одного монолитного промпта работа разбита на команду специализированных агентов и автоматических рецензентов (**autoraters**).

---

## 🏗️ 2. Архитектура агентов и оценка качества (`methods/` + `autoraters/`)

```text
Raw Materials (идея + логи экспериментов) + LaTeX Template (CVPR / ICLR)
   │
   ├──► 1. Outline Agent (`outline_agent.py`)          — структура будущей статьи
   ├──► 2. Literature Review Agent (`scholar_utils.py`) — поиск в Semantic Scholar и синтез обзора
   ├──► 3. Plotting Agent (`plotting_agent.py`)        — графики из кода + концептуальные схемы
   ├──► 4. Section Writing Agent (`section_writing_agent.py`) — написание разделов в LaTeX
   └──► 5. Content Refinement + Format (`content_refinement_agent.py`) — шлифовка, стиль и сборка
           │
           ▼
   Autoraters (`autoraters/`):
   • `citation_f1.py`          — проверка точности и полноты ссылок
   • `lit_review_quality.py`   — качество литературного обзора
   • `agent_review.py`         — симулированное рецензирование статьи
   • `sxs_paper_quality.py`    — Side-by-Side сравнение версий
```

### Ключевые инженерные особенности
* **Разделение моделей генерации и критики:** в CLI явно задаются отдельно `--writer_model_name` (написание текста и обзор литературы) и `--reflection_model_name` (рефлексия и правка).
* **Конференц-шаблоны из коробки:** в `templates/` лежат полные пакеты оформления **CVPR 2025** и **ICLR 2025** (`.sty`, `.bst`, `guidelines.md`, `template.tex`), куда легко добавить свой шаблон.
* **Генерация иллюстраций (`--use_plotting true`):** `paper_writer_with_plotting.py` и `utils/paper_banana_utils.py` позволяют строить графики из данных и вставлять концептуальные диаграммы.
* **Интерактивный UI:** есть веб-интерфейс на Streamlit (`frontend/app.py`) с примером `cvpr_example`.
* *Примечание:* тестовый датасет для бенчмаркинга в репозиторий не включён и публикуется отдельно.

---

## 🚀 3. Установка и запуск

```bash
conda create -n paper_orchestra python=3.11 && conda activate paper_orchestra
pip install -r requirements.txt

# В .env указываются ключи: SEMANTIC_SCHOLAR_API_KEY, GEMINI_API_KEY / VERTEX_AI_* или OPENAI_API_KEY
python paper_writing_cli.py \
  --raw_materials_dir /path/to/raw_materials/ \
  --latex_template_dir templates/cvpr2025 \
  --output_dir ./out_paper \
  --use_plotting true
```

---

## 🔗 4. Синергия с базой знаний

* **Связка с [Academic Research Skills](file:///home/blackzeshi/Documents/Notes/04_scientific_research_and_discovery/academic-research-skills.md) и [Hyperresearch](file:///home/blackzeshi/Documents/Notes/04_scientific_research_and_discovery/hyperresearch.md):** если Hyperresearch сфокусирован на глубоком поиске и проверке гипотез, то PaperOrchestra даёт чистую архитектуру **мультиагентного LaTeX-писателя** с отдельной линейкой `autoraters/` (`citation_f1`, SxS-оценка).
* **Связка с [alphaXiv OpenResearch](file:///home/blackzeshi/Documents/Notes/04_scientific_research_and_discovery/openresearch.md):** логичное финальное звено после экспериментов в OpenResearch для упаковки результатов в макеты ICLR/CVPR.
