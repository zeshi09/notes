---
title: "Scientific Agent Skills (K-Dense AI: 165 научных навыков и 100+ баз)"
repo: "https://github.com/K-Dense-AI/scientific-agent-skills"
category: "04_scientific_research_and_discovery"
tags: [ai-science, agent-skills, biology, chemistry, drug-discovery, pubmed, alphafold]
stars: "41.3k+"
date: 2026-08-31
---

# 🔬 Scientific Agent Skills (K-Dense AI)

> **Ссылка на репозиторий:** [https://github.com/K-Dense-AI/scientific-agent-skills](https://github.com/K-Dense-AI/scientific-agent-skills)  
> **Организация:** K-Dense AI  
> **Звёзды GitHub:** 40,500+ ★ (Используется 190,000+ ученых по всему миру)  
> **Стандарты:** Совместимо со стандартом [Agent Skills](https://agentskills.io/) и [Agent Plugins](https://agent-plugins.org/)  
> **Поддерживаемые клиенты:** Claude Code, Google Antigravity, OpenAI Codex, Cursor, Pi  
> **Лицензия:** MIT  

---

## 🎯 1. В чем главная ценность?

**Scientific Agent Skills** — это крупнейшая в мире библиотека открытых, верифицированных и готовых к установке навыков (**165+ валидированных скиллов**) и коннекторов к **100+ научным базам данных**, которая превращает любого стандартного AI-агента в автономного ученого-исследователя в области биологии, химии, медицины, биоинформатики и дизайна лекарств.

---

## 🧬 2. Структура библиотеки навыков

```text
┌────────────────────────────────────────────────────────────────────────┐
│                        SCIENTIFIC AGENT SKILLS                         │
│                                                                        │
│  🧪 БИОЛОГИЯ И ГЕНОМИКА:                                               │
│  • NCBI / BLAST / Ensembl API интеграции                               │
│  • Анализ single-cell RNA-seq данных (Scanpy, Seurat)                  │
│  • Предсказание структур белков через AlphaFold / ESMFold              │
│                                                                        │
│  💊 ХИМИЯ И ДИЗАЙН ЛЕКАРСТВ (Drug Discovery):                         │
│  • Поиск по ChEMBL, PubChem, DrugBank, PDB                             │
│  • Расчет молекулярных дескрипторов (RDKit)                            │
│  • Молекулярный докинг (AutoDock Vina) и скрининг лигандов             │
│                                                                        │
│  📚 НАУЧНЫЙ ПОИСК И СИНТЕЗ ЛИТЕРАТУРЫ:                                 │
│  • Прямой парсинг PubMed, bioRxiv, medRxiv, Europe PMC                 │
│  • Извлечение структурированных фактов и таблиц из PDF                 │
│  • Построение семантических карт доказательств (Evidence Trees)        │
└────────────────────────────────────────────────────────────────────────┘
```

---

## 💻 3. Как подключить к своим AI-агентам?

Библиотека написана в стандартном формате Agent Skills и подключается за секунды:

```bash
# Установка через менеджер скиллов
npx agent-skills install @k-dense/scientific-agent-skills

# Или прямое клонирование в каталог .agents вашего проекта:
git clone --depth 1 https://github.com/K-Dense-AI/scientific-agent-skills.git .agents/skills/science
```

После этого ваш агент (в Claude Code, Antigravity или Codex) автоматически получает доступ к специализированным научным тулам (`blast_sequence`, `query_chembl`, `dock_molecule`, `search_pubmed_papers`).

---
*Заметка сохранена: 2026-08-31 в /home/blackzeshi/Documents/Notes/scientific-agent-skills.md*