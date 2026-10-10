# 🧭 База знаний и заметок по AI-инженерии, агентам и софту

> **Каталог заметок по передовым GitHub репозиториям и архитектурным паттернам.**
> Структура организована по тематическим категориям с поддержкой YAML Frontmatter тегирования (совместимо с Obsidian, Logseq, VS Code).

🎯 **Главный стратегический документ:** [🚀 Capstone Roadmap: Превращение базы знаний в автономную исследовательскую лабораторию](00_strategy_and_roadmaps/capstone-engineering-roadmap.md)
🛡️ **Архитектурный стандарт безопасности агентов:** [🛡️ TCB & Reference Monitor: Полное руководство](05_security_osint_and_guardrails/tcb-agent-security.md)
🔀 **Архитектура шлюзов и брокеров тулов:** [🔀 Архитектура Tool Broker & Execution Blocker](02_agent_runtimes_and_harnesses/tool-broker-architecture.md)

---

## 📂 Тематические категории

### 🚀 00. Стратегия, дорожные карты и Capstone-проекты
*Сквозные роадмапы превращения базы знаний в практическую инженерную экспертизу, исчерпывающие конспекты канонического системного дизайна (System Design Notes по книгам Алекса Сю), сборники технических интервью и системного дизайна AI (AI Engineering Interviews), системные руководства по непрерывному обучению в эпоху AI (Up Хань Сянькая) и работающие продукты.*

| Заметка | Репозиторий | Звёзды | Теги |
| :--- | :--- | :--- | :--- |
| 📄 **[AI Engineering Interviews: Всеобъемлющий сборник вопросов и системного дизайна для AI-инженеров](00_strategy_and_roadmaps/ai-engineering-interviews.md)** | [pallavi-shekhar/ai-engineering-interview-questions-company-wise](https://github.com/pallavi-shekhar/ai-engineering-interview-questions-company-wise) | `940+` | `#ai-engineering` `#interview-prep` `#system-design` `#llm-infra` `#vllm` `#rag` `#career-roadmap` `#curated-list` |
| 📄 **[Capstone Roadmap: Как превратить базу знаний в персональную исследовательскую лабораторию](00_strategy_and_roadmaps/capstone-engineering-roadmap.md)** | [knowledge-base/strategy](local://knowledge-base/strategy) | `Master-Plan` | `#learning-roadmap` `#capstone-project` `#ai-engineering` `#autonomous-research` `#strategy` `#system-architecture` |
| 📄 **[System Design Notes: Полный конспект и архитектурный справочник бестселлера Алекса Сю (Vol 1 & Vol 2)](00_strategy_and_roadmaps/system-design-notes.md)** | [liquidslr/system-design-notes](https://github.com/liquidslr/system-design-notes) | `24.0k+` | `#system-design` `#distributed-systems` `#architecture` `#scalability` `#bytebytego` `#alex-xu` `#faang-interview` `#database-sharding` `#high-availability` |
| 📄 **[Up (人生进阶指南): Системное руководство по непрерывному обучению, созданию продуктов и карьере в эпоху AI](00_strategy_and_roadmaps/up.md)** | [byoungd/up](https://github.com/byoungd/up) | `67.0k+` | `#up` `#career-roadmap` `#lifelong-learning` `#ai-engineering` `#systems-thinking` `#personal-growth` `#evidence-based` `#problem-solving` |

### 🧠 01. Архитектура LLM и обучение моделей с нуля
*Трансформеры с нуля, модели рассуждения (DeepSeek-R1/GRPO), контрастивные модели действий System-1 (CLM), системный дизайн AI-инфраструктуры (AI Infra Book Ли Боцзе), ультралегкие LLM (MiniMind), мультиязычные неавторегрессионные движки решений (Laya), фундаментальные курсы (Dive into LLMs), полностековые роадмапы (LLM Master), локальный System-1 Option-Attention (OpenJev, Kev) и сквозная AI-инженерия.*

| Заметка | Репозиторий | Звёзды | Теги |
| :--- | :--- | :--- | :--- |
| 📄 **[LLMs from Scratch (Себастьян Рашка)](01_llm_architecture_and_training/LLMs-from-scratch.md)** | [rasbt/LLMs-from-scratch](https://github.com/rasbt/LLMs-from-scratch) | `47.5k+` | `#llm` `#pytorch` `#transformers` `#from-scratch` `#education` `#deep-learning` |
| 📄 **[AI Engineering from Scratch (Рохит Гумаре: 511 уроков, 20 фаз)](01_llm_architecture_and_training/ai-engineering-from-scratch.md)** | [blackzeshi/Git/ai-engineering-from-scratch](https://github.com/blackzeshi/Git/ai-engineering-from-scratch) | `57.2k+` | `#ai-engineering` `#roadmap` `#mcp` `#vllm` `#grpo` `#rag` `#agent-orchestration` |
| 📄 **[AI Infra Book: Количественный анализ и системный дизайн AI-инфраструктуры (Ли Боцзе / Bojie Li)](01_llm_architecture_and_training/ai-infra-book.md)** | [bojieli/ai-infra-book](https://github.com/bojieli/ai-infra-book) | `2.2k+` | `#ai-infra-book` `#ai-infrastructure` `#system-design` `#hardware-constraints` `#kv-cache` `#roofline-model` `#distributed-inference` `#distributed-training` `#rdma` `#vllm` `#bojie-li` `#open-source-book` |
| 📄 **[CLM: Фреймворк контрастивного обучения языковых моделей и оптимизации семантических представлений](01_llm_architecture_and_training/clm.md)** | [Contrastive-LM/CLM](https://github.com/Contrastive-LM/CLM) | `1.1k+` | `#clm` `#contrastive-learning` `#embeddings` `#infonce` `#representation-learning` `#rag` `#semantic-search` `#python` `#pytorch` |
| 📄 **[Dive into LLMs (动手学大模型): Практический курс инженерии больших языковых моделей](01_llm_architecture_and_training/dive-into-llms.md)** | [Lordog/dive-into-llms](https://github.com/Lordog/dive-into-llms) | `51.3k+` | `#llm` `#transformers` `#pretraining` `#sft` `#lora` `#rlhf` `#dpo` `#quantization` `#vllm` `#deep-learning` `#jupyter` |
| 📄 **[Kev: Компактная System-1 модель Option-Attention на базе Qwen2.5-0.5B для обучения и запуска на MacBook](01_llm_architecture_and_training/kev.md)** | [jaredpalmer/kev](https://github.com/jaredpalmer/kev) | `2.9k+` | `#kev` `#jaredpalmer` `#option-attention` `#system-1-models` `#qwen` `#local-training` `#macbook` `#apple-silicon` `#mlx` `#pytorch` `#python` |
| 📄 **[Laya: Неавторегрессионный мультиязычный System-1 движок типизированных решений (100+ языков за 33 мс)](01_llm_architecture_and_training/laya.md)** | [NandhaKishorM/laya](https://github.com/NandhaKishorM/laya) | `13.6k+` | `#laya` `#system-1-models` `#non-autoregressive` `#typed-decisions` `#rlcd` `#multilingual-ai` `#option-attention` `#direct-logits` `#inference-optimization` `#python` |
| 📄 **[LLM-Master: Полностековая инженерная дорожная карта и учебник по LLM, RAG и Agent](01_llm_architecture_and_training/llm-master.md)** | [youngyangyang04/llm-master](https://github.com/youngyangyang04/llm-master) | `400+` | `#llm-master` `#llm-roadmap` `#prompt-engineering` `#rag` `#ai-agents` `#mcp` `#fine-tuning` `#vllm` `#transformers` `#interview-prep` `#system-design` |
| 📄 **[MiniMind: Обучение собственной LLM (64M) с нуля за 2 часа](01_llm_architecture_and_training/minimind.md)** | [jingyaogong/minimind](https://github.com/jingyaogong/minimind) | `56.7k+` | `#llm` `#pretraining` `#sft` `#lora` `#dpo` `#lightweight-models` `#pytorch` |
| 📄 **[OpenJev: Локальные System-1 модели для мгновенного принятия решений без генерации токенов](01_llm_architecture_and_training/openjev.md)** | [TheoLeeCJ/openjev](https://github.com/TheoLeeCJ/openjev) | `460+` | `#openjev` `#option-attention` `#system-1-models` `#decision-making` `#direct-logits` `#local-llm` `#qwen` `#inference-optimization` `#python` `#pytorch` |
| 📄 **[Reasoning from Scratch (Себастьян Рашка: DeepSeek-R1, GRPO, RLVR)](01_llm_architecture_and_training/reasoning-from-scratch.md)** | [rasbt/reasoning-from-scratch](https://github.com/rasbt/reasoning-from-scratch) | `18.2k+` | `#reasoning` `#deepseek-r1` `#grpo` `#rlvr` `#reinforcement-learning` `#inference-scaling` |

### 🤖 02. Агентные рантаймы, харнесы и оркестрация
*Универсальный локальный AI-шлюз и роутер квот для кодинг-агентов (Magpie), декларативные OCI-рантаймы, песочницы и паспорта безопасности агентов от Docker Engineering (Docker Agent), официальный стек корпоративных ролевых плагинов Anthropic (Claude Knowledge Work Plugins), инженерное менторство и сохранение контроля при вайб-кодинге (VibeWise), мышление сеньора и анти-оверинжиниринг (Ponytail), дизайн-системы и правила верстки AI-агентов (Impeccable Пола Бакауса), визуальные HTML-ответы с экономией токенов (Answer Me with HTML), постоянные цифровые коллеги с виртуальными ПК (OpenDots), самообучающиеся слои навыков кодинг-агентов (AutoHarness), операционные системы управления штатом агентов (Paperclip), самообучающаяся долговременная память (Hindsight), непрерывное обучение агентов (Reef), офисные рантаймы документов (Univer), кластерные оркестраторы от Google (AX), кросс-агентная память на Rust (AI-Memory), децентрализованные P2P-сети агентов (EnvoyMesh), управляемое исполнение (Evenfire), экранные копилоты (Jev-Chat Jarvis), экосистемы Option-Attention (Awesome-Jev), ультрабыстрые браузерные агенты (Jev Ultrafast), спецификации (OpenSpec) и учебники по агентам.*

| Заметка | Репозиторий | Звёзды | Теги |
| :--- | :--- | :--- | :--- |
| 📄 **[Agent-Reach: Универсальный интернет-шлюз и сборщик контента для AI-агентов с нулевыми затратами на API](02_agent_runtimes_and_harnesses/agent-reach.md)** | [Panniantong/Agent-Reach](https://github.com/Panniantong/Agent-Reach) | `79.9k+` | `#agent-reach` `#web-scraping` `#agent-eyes` `#multi-platform` `#zero-api-fees` `#fallback-routing` `#twitter` `#reddit` `#youtube` `#bilibili` `#github` `#mcp` |
| 📄 **[Agent-Skills: Защищенный и верифицированный реестр навыков для кодинг-агентов (Tech Leads Club)](02_agent_runtimes_and_harnesses/agent-skills.md)** | [tech-leads-club/agent-skills](https://github.com/tech-leads-club/agent-skills) | `5.9k+` | `#agent-skills` `#skill-registry` `#antigravity` `#claude-code` `#cursor` `#supply-chain-security` `#verified-skills` `#mcp` `#spec-driven` `#typescript` `#snyk-agent-scan` |
| 📄 **[AI Agent Book: Архитектура, инженерия харнесов и промышленная практика (Ли Боцзе / Bojie Li)](02_agent_runtimes_and_harnesses/ai-agent-book.md)** | [bojieli/ai-agent-book](https://github.com/bojieli/ai-agent-book) | `46.2k+` | `#ai-agent-book` `#harness-engineering` `#context-engineering` `#mcp` `#coding-agents` `#multi-agent` `#agent-evals` `#post-training` `#continuous-evolution` `#kv-cache` `#bojie-li` `#open-source-book` |
| 📄 **[AI-Memory: Вендоро-независимая долговременная память и бесшовный handoff контекста между кодинг-агентами](02_agent_runtimes_and_harnesses/ai-memory.md)** | [akitaonrails/ai-memory](https://github.com/akitaonrails/ai-memory) | `7.9k+` | `#ai-memory` `#agent-memory` `#context-handoff` `#claude-code` `#codex` `#cursor` `#long-term-memory` `#git-integration` `#rust` `#ai-coding` |
| 📄 **[Answer Me with HTML: Навык интерактивной визуализации ответов AI-агентов с экономией 85% токенов](02_agent_runtimes_and_harnesses/answer-me-with-html.md)** | [QingYunA/answer-me-with-html](https://github.com/QingYunA/answer-me-with-html) | `750+` | `#answer-me-with-html` `#agent-skill` `#claude-code` `#codex` `#cursor` `#data-visualization` `#html-reporting` `#token-optimization` `#prompt-engineering` |
| 📄 **[ArcBox: Изолированные контейнеры и микро-VM для AI-Агентов на Rust](02_agent_runtimes_and_harnesses/arcbox.md)** | [arcboxlabs/arcbox](https://github.com/arcboxlabs/arcbox) | `1.9k+` | `#sandboxing` `#rust` `#micro-vm` `#containers` `#oci` `#agent-security` |
| 📄 **[Atlas: Система контроля версий (VCS) для параллельных AI-агентов на Rust](02_agent_runtimes_and_harnesses/atlas.md)** | [pacifio/atlas](https://github.com/pacifio/atlas) | `2.1k+` | `#vcs` `#ai-agents` `#rust` `#tree-sitter` `#ast-merge` `#source-control` |
| 📄 **[AutoHarness: Самообучающийся слой навыков для кодинг-агентов (Self-Learning Skill Layer)](02_agent_runtimes_and_harnesses/autoharness.md)** | [tigerless-labs/autoharness](https://github.com/tigerless-labs/autoharness) | `4.6k+` | `#autoharness` `#claude-code` `#skill-learning` `#agent-harness` `#continual-learning` `#core-bench` `#python` `#self-improving` |
| 📄 **[Awesome DESIGN.md: Спецификации дизайн-систем для AI-агентов кодинга](02_agent_runtimes_and_harnesses/awesome-design-md.md)** | [VoltAgent/awesome-design-md](https://github.com/VoltAgent/awesome-design-md) | `113.5k+` | `#design-systems` `#ai-coding` `#claude-code` `#cursor` `#codex` `#ui-ux` `#prompt-engineering` `#frontend` |
| 📄 **[Awesome-Jev: Экосистемный курируемый каталог архитектуры Option-Attention и System-1 агентов (430+ проектов)](02_agent_runtimes_and_harnesses/awesome-jev.md)** | [heyjunpenn/awesome-jev](https://github.com/heyjunpenn/awesome-jev) | `300+` | `#awesome-jev` `#option-attention` `#jev-ecosystem` `#curated-list` `#system-1` `#non-autoregressive` `#browser-agents` `#decision-engine` `#catalog` |
| 📄 **[Claude Knowledge Work Plugins: Официальный стек плагинов Anthropic для Claude Cowork и Claude Code](02_agent_runtimes_and_harnesses/claude-knowledge-work-plugins.md)** | [anthropics/knowledge-work-plugins](https://github.com/anthropics/knowledge-work-plugins) | `27.0k+` | `#claude-plugins` `#claude-cowork` `#claude-code` `#anthropic` `#mcp` `#knowledge-work` `#agent-skills` `#enterprise-ai` `#productivity` |
| 📄 **[Diagram Design: 39 журнальных типов диаграмм на чистом HTML+SVG для AI-агентов](02_agent_runtimes_and_harnesses/diagram-design.md)** | [cathrynlavery/diagram-design](https://github.com/cathrynlavery/diagram-design) | `30.2k+` | `#data-visualization` `#diagrams` `#html` `#svg` `#ai-agents` `#claude-code` `#codex` `#no-mermaid` |
| 📄 **[Docker Agent: Декларативный OCI-рантайм, песочницы и паспорта безопасности для AI-агентов (Docker Engineering)](02_agent_runtimes_and_harnesses/docker-agent.md)** | [docker/docker-agent](https://github.com/docker/docker-agent) | `4.2k+` | `#docker-agent` `#agent-passport` `#threat-modeling` `#tcb` `#sandboxing` `#oci-runtime` `#permissions` `#mcp` `#google-ax` `#zero-trust` `#go` |
| 📄 **[Dormice: «SQLite среди песочниц» — Self-Hosted долгоживущие песочницы для AI-агентов](02_agent_runtimes_and_harnesses/dormice.md)** | [BitMiracle-AI/Dormice](https://github.com/BitMiracle-AI/Dormice) | `1.0k+` | `#agent-sandbox` `#self-hosted` `#e2b-compatible` `#gvisor` `#docker` `#typescript` `#idle-zero-cost` |
| 📄 **[EnvoyMesh: Децентрализованная P2P-сеть для автономных AI-агентов с суверенной идентичностью (SSI)](02_agent_runtimes_and_harnesses/envoymesh.md)** | [allenpeng0705/EnvoyMesh](https://github.com/allenpeng0705/EnvoyMesh) | `1.5k+` | `#envoymesh` `#p2p-mesh` `#decentralized-agents` `#ssi` `#self-sovereign-identity` `#agent-to-agent` `#typescript` `#peer-to-peer` `#edge-ai` |
| 📄 **[Evenfire: Защищенная платформа исполнения транзакционных действий AI-агентов на приватной инфраструктуре](02_agent_runtimes_and_harnesses/evenfire.md)** | [evenfire-ai/evenfire](https://github.com/evenfire-ai/evenfire) | `360+` | `#evenfire` `#action-execution` `#agent-runtime` `#enterprise-guardrails` `#api-gateway` `#rbac` `#self-hosted` `#typescript` `#workflow-automation` |
| 📄 **[Google AX: Декларативный кластерный оркестратор агентных воркфлоу (Kubernetes для AI-агентов)](02_agent_runtimes_and_harnesses/google-ax.md)** | [google/ax](https://github.com/google/ax) | `6.6k+` | `#google-ax` `#agent-orchestration` `#cluster-runtime` `#declarative-workflows` `#agent-substrate` `#sandboxing` `#go` `#kubernetes-for-agents` `#enterprise-ai` |
| 📄 **[Hindsight: Самообучающаяся долговременная память для автономных AI-агентов (arXiv:2512.12818)](02_agent_runtimes_and_harnesses/hindsight.md)** | [vectorize-io/hindsight](https://github.com/vectorize-io/hindsight) | `28.8k+` | `#hindsight` `#agent-memory` `#continual-learning` `#episodic-memory` `#vector-search` `#arxiv` `#ai-agent` `#python` |
| 📄 **[i-have-adhd: Скилл и поведенческий слой для кодинг-агентов (ADHD-friendly output без «воды»)](02_agent_runtimes_and_harnesses/i-have-adhd.md)** | [ayghri/i-have-adhd](https://github.com/ayghri/i-have-adhd) | `42.5k+` | `#agent-skills` `#prompt-engineering` `#ux` `#productivity` `#claude-code` `#cursor` `#codex` `#adhd` `#formatting` |
| 📄 **[Impeccable: Дизайн-система, 24 команды и 61 правило верстки для AI-кодинг агентов от Пола Бакауса](02_agent_runtimes_and_harnesses/impeccable.md)** | [pbakaus/impeccable](https://github.com/pbakaus/impeccable) | `75.8k+` | `#impeccable` `#paul-bakaus` `#design-system` `#vibe-coding` `#frontend` `#claude-code` `#cursor` `#codex` `#linting` `#ui-ux` `#design-quality` |
| 📄 **[Jev-Chat Jarvis: Неинвазивный экранный диалоговый AI-копилот для Android через Option-Attention](02_agent_runtimes_and_harnesses/jev-chat-jarvis.md)** | [jev-chat/jev-chat-jarvis](https://github.com/jev-chat/jev-chat-jarvis) | `2.7k+` | `#jev-chat-jarvis` `#mobile-agent` `#android` `#kotlin` `#option-attention` `#non-invasive` `#accessibility-api` `#chat-copilot` `#system-1` |
| 📄 **[Jev Ultrafast: Сверхбыстрый браузерный агент на базе Option-Attention и динамического пространства действий](02_agent_runtimes_and_harnesses/jev-ultrafast.md)** | [browser-use/jev-ultrafast](https://github.com/browser-use/jev-ultrafast) | `1.2k+` | `#jev-ultrafast` `#browser-use` `#browser-agent` `#option-attention` `#system-1` `#web-automation` `#ultrafast` `#agent-harness` `#python` |
| 📄 **[Learn Harness Engineering (Курс WalkingLabs: 14 лекций, 8 проектов)](02_agent_runtimes_and_harnesses/learn-harness-engineering.md)** | [walkinglabs/learn-harness-engineering](https://github.com/walkinglabs/learn-harness-engineering) | `12.8k+` | `#harness-engineering` `#ai-agents` `#mcp` `#agent-architecture` `#audit-harness` |
| 📄 **[M3E Canvas: Браузерный конструктор экранов Material 3 Expressive с генерацией промптов для вайб-кодинга](02_agent_runtimes_and_harnesses/m3e-canvas.md)** | [lnkiai/m3e-canvas](https://github.com/lnkiai/m3e-canvas) | `880+` | `#vibe-coding` `#prompt-engineering` `#ui-ux` `#material-design` `#react` `#prototyping` `#ai-coding` `#canvas` |
| 📄 **[Magpie: Универсальный локальный AI-шлюз и роутер квот для кодинг-агентов (Claude Code, Codex, OpenCode)](02_agent_runtimes_and_harnesses/magpie.md)** | [yetone/magpie](https://github.com/yetone/magpie) | `8.5k+` | `#magpie` `#ai-gateway` `#claude-code` `#codex` `#opencode` `#quota-failover` `#intent-routing` `#prompt-cache` `#model-routing` `#cost-optimization` `#go` `#typescript` |
| 📄 **[Monty: Минималистичный и безопасный интерпретатор Python на Rust для AI-агентов](02_agent_runtimes_and_harnesses/monty.md)** | [pydantic/monty](https://github.com/pydantic/monty) | `8.2k+` | `#python-interpreter` `#rust` `#agent-sandbox` `#code-mode` `#pydantic` `#programmatic-tool-calling` `#security` `#micro-runtime` |
| 📄 **[Open Code Review: Промышленный гибридный инструмент код-ревью от Alibaba (Deterministic Engineering × Agent)](02_agent_runtimes_and_harnesses/open-code-review.md)** | [alibaba/open-code-review](https://github.com/alibaba/open-code-review) | `25.2k+` | `#open-code-review` `#alibaba` `#code-review` `#deterministic-engineering` `#agent-hybrid` `#ast-analysis` `#line-level-precision` `#token-efficiency` `#git-diff` `#security-rules` `#go` `#aacr-bench` |
| 📄 **[OpenDots: Автономные цифровые коллеги с собственными виртуальными ПК и интерфейсом Spaces (CopilotKit)](02_agent_runtimes_and_harnesses/opendots.md)** | [CopilotKit/OpenDots](https://github.com/CopilotKit/OpenDots) | `2.9k+` | `#opendots` `#copilotkit` `#ai-coworkers` `#autonomous-agents` `#agent-workspace` `#openbot` `#human-in-the-loop` `#slack` `#typescript` |
| 📄 **[OpenMAIC: Мульти-агентная интерактивная аудитория (Цинхуа)](02_agent_runtimes_and_harnesses/openmaic.md)** | [THU-MAIC/OpenMAIC](https://github.com/THU-MAIC/OpenMAIC) | `28.9k+` | `#multi-agent` `#education` `#typescript` `#webrtc` `#interactive-learning` |
| 📄 **[OpenSpec: Спецификационно-ориентированная разработка (SDD) для AI кодинг-ассистентов](02_agent_runtimes_and_harnesses/openspec.md)** | [Fission-AI/OpenSpec](https://github.com/Fission-AI/OpenSpec) | `68.8k+` | `#openspec` `#spec-driven-development` `#sdd` `#coding-agents` `#context-engineering` `#claude-code` `#cursor` `#specs` `#planning` `#typescript` |
| 📄 **[Paperclip: Открытая операционная система управления штатом AI-агентов (Workforce OS)](02_agent_runtimes_and_harnesses/paperclip.md)** | [paperclipai/paperclip](https://github.com/paperclipai/paperclip) | `83.8k+` | `#paperclip` `#agent-workforce` `#agent-orchestration` `#enterprise-ai` `#multi-agent` `#workflow-automation` `#typescript` `#react` `#self-hosted` |
| 📄 **[Ponytail: Скилл ленивого сеньор-разработчика для агентов — сокращение кода на 54% и YAGNI без оверинжиниринга](02_agent_runtimes_and_harnesses/ponytail.md)** | [DietrichGebert/ponytail](https://github.com/DietrichGebert/ponytail) | `154.2k+` | `#ponytail` `#senior-dev` `#yagni` `#agent-skills` `#claude-code` `#cursor` `#prompt-engineering` `#code-reduction` `#minimal-code` |
| 📄 **[Reef: Открытая инфраструктура непрерывного обучения (Continual Learning) и сохранения опыта агентов](02_agent_runtimes_and_harnesses/reef.md)** | [Human-Agent-Society/reef](https://github.com/Human-Agent-Society/reef) | `5.1k+` | `#reef` `#continual-learning` `#agent-memory` `#experience-replay` `#catastrophic-forgetting` `#trajectory-logging` `#human-agent-society` `#python` |
| 📄 **[SoL-Pi: Оптимизация агентных харнесов и исследовательских циклов от Nvidia Research](02_agent_runtimes_and_harnesses/sol-pi.md)** | [NVlabs/SoL-Pi](https://github.com/NVlabs/SoL-Pi) | `1.3k+` | `#nvidia` `#agent-harness` `#efficiency` `#context-compression` `#action-fusion` `#observation-pack` `#pi-agent` `#auto-research` `#token-diet` |
| 📄 **[Архитектура Tool Broker & Execution Blocker: Проектирование шлюзов вызова и защиты инструментов AI-агентов](02_agent_runtimes_and_harnesses/tool-broker-architecture.md)** | [agent-architecture/tool-broker](local://agent-architecture/tool-broker) | `Master-Architecture` | `#tool-broker` `#tool-gateway` `#mcp-router` `#agent-runtime` `#tool-rag` `#lethal-trifecta` `#loop-breaker` `#security` `#credential-offloading` |
| 📄 **[Univer: Офисный рантайм и харнес для AI-агентов (Таблицы, Документы, Слайды, Canvas, PDF)](02_agent_runtimes_and_harnesses/univer.md)** | [dream-num/univer](https://github.com/dream-num/univer) | `18.2k+` | `#univer` `#office-harness` `#spreadsheets` `#docs` `#slides` `#canvas` `#pdf` `#agent-runtime` `#typescript` `#ui-components` |
| 📄 **[VibeWise: Интерактивный ментор для кодинг-агентов — предотвращение деградации инженера в эпоху Vibe-кодинга](02_agent_runtimes_and_harnesses/vibe-wise.md)** | [nykooi1/vibe-wise](https://github.com/nykooi1/vibe-wise) | `1.3k+` | `#vibe-wise` `#claude-code` `#claude-plugin` `#vibe-coding` `#engineering-mentorship` `#active-learning` `#software-design` `#human-in-the-loop` `#python` |
| 📄 **[ZeroBoot: Суб-миллисекундные песочницы микро-VM для AI-агентов на чистом Rust](02_agent_runtimes_and_harnesses/zeroboot.md)** | [zerobootdev/zeroboot](https://github.com/zerobootdev/zeroboot) | `2.4k+` | `#agent-sandbox` `#rust` `#micro-vm` `#copy-on-write` `#virtualization` `#code-execution` `#high-performance` |
| 📄 **[zvec-grep (zg): Локальный гибридный поиск по кодовой базе для людей и AI-агентов](02_agent_runtimes_and_harnesses/zvec-grep.md)** | [zvec-ai/zvec-grep](https://github.com/zvec-ai/zvec-grep) | `1.8k+` | `#search` `#local-first` `#semantic-search` `#vector-search` `#ai-agents` `#code-search` `#bm25` `#hybrid-search` |

### 🏛️ 03. Графы знаний, контекст и онтологии
*Высокоскоростные графовые СУБД на Rust поверх объектных S3 хранилищ (HydraDB), графовая инфраструктура контекста (Semantica AGI) и Enterprise World Model воркбенчи на Rust (Utopia).*

| Заметка | Репозиторий | Звёзды | Теги |
| :--- | :--- | :--- | :--- |
| 📄 **[HydraDB: Высокоскоростная графовая база данных на Rust поверх объектных S3-хранилищ](03_knowledge_graphs_and_ontologies/hydradb.md)** | [hydra-db/hydradb](https://github.com/hydra-db/hydradb) | `6.4k+` | `#hydradb` `#graph-database` `#rust` `#opencypher` `#s3-storage` `#object-storage` `#knowledge-graphs` `#enterprise-data` |
| 📄 **[Semantica AGI: Графовая инфраструктура контекста и подотчетности](03_knowledge_graphs_and_ontologies/semantica.md)** | [semantica-agi/semantica](https://github.com/semantica-agi/semantica) | `11.4k+` | `#knowledge-graphs` `#prov-o` `#decision-intelligence` `#datalog` `#shacl` `#rete` |
| 📄 **[Utopia: Open-Source Enterprise World Model & Ontology Workbench](03_knowledge_graphs_and_ontologies/utopia.md)** | [deeplethe/utopia](https://github.com/deeplethe/utopia) | `1.3k+` | `#ontologies` `#world-model` `#rust` `#local-first` `#mcp` `#knowledge-graphs` |

### 🔬 04. Автономные исследования и AI for Science
*Local-First воркспейсы для научных агентов на Rust (alphaXiv OpenResearch), автономные исследовательские харнесы (Hyperresearch), академические скиллы полного цикла (Academic Research Skills), библиотеки специализированных тулов (165+ скиллов) и автономные лаборатории (PRAXIST).*

| Заметка | Репозиторий | Звёзды | Теги |
| :--- | :--- | :--- | :--- |
| 📄 **[Academic Research Skills: Полный цикл научных исследований для Claude Code](04_scientific_research_and_discovery/academic-research-skills.md)** | [Imbad0202/academic-research-skills](https://github.com/Imbad0202/academic-research-skills) | `45.5k+` | `#academic-research` `#claude-code` `#scientific-writing` `#peer-review` `#latex` `#citation-audit` `#socratic-planning` |
| 📄 **[Hyperresearch: Автономный Deep Research харнес с самообучающимся хранилищем и 16-шаговым конвейером](04_scientific_research_and_discovery/hyperresearch.md)** | [jordan-gibbs/hyperresearch](https://github.com/jordan-gibbs/hyperresearch) | `2.9k+` | `#deep-research` `#academic-research` `#claude-code` `#agents` `#mcp` `#knowledge-vault` `#web-scraping` `#peer-review` `#citation-verification` |
| 📄 **[alphaXiv OpenResearch: Local-First воркспейс на Rust для автономных научных исследований (Autoresearch)](04_scientific_research_and_discovery/openresearch.md)** | [alphaXiv/OpenResearch](https://github.com/alphaXiv/OpenResearch) | `4.2k+` | `#openresearch` `#alphaxiv` `#autoresearch` `#research-agents` `#rust` `#orx-cli` `#arxiv` `#git-worktrees` `#experiment-tracking` `#reproducible-research` `#claude-code` `#cursor` |
| 📄 **[PRAXIST: Автономный исследовательский R&D фреймворк](04_scientific_research_and_discovery/praxist.md)** | [sapientinc/PRAXIST](https://github.com/sapientinc/PRAXIST) | `5.4k+` | `#autonomous-research` `#evolutionary-search` `#r-and-d` `#evidence-ledger` `#arxiv` |
| 📄 **[Scientific Agent Skills (K-Dense AI: 165 научных навыков и 100+ баз)](04_scientific_research_and_discovery/scientific-agent-skills.md)** | [K-Dense-AI/scientific-agent-skills](https://github.com/K-Dense-AI/scientific-agent-skills) | `41.3k+` | `#ai-science` `#agent-skills` `#biology` `#chemistry` `#drug-discovery` `#pubmed` `#alphafold` |

### 🛡️ 05. Кибербезопасность, OSINT и тестирование барьеров
*Автономный агентный пентестинг и шлюзы согласования Human-in-the-Loop (ARTEX), дорожные карты наступательной безопасности AI/ML, Prompt Injection и MCP (AI-ML Pentest Roadmap Анмола Сачана), безопасный рантайм ядра и формальная верификация политик агентов от NVIDIA (OpenShell), энциклопедия прокси, туннелей и механизмов обхода DPI/GFW (FQ-Book), аппаратные микро-ВМ песочницы для кодинг-агентов (Coop от Trail of Bits), агентные навыки реверс-инжиниринга Android APK (APK-Reverse), AI-Native AppSec экосистема и MITM-прокси (Ghost Security: Reaper, Poltergeist, Wraith), анатомия ядра Linux и контейнеры (Linux Insides & NCC Group), шестифазный аудит уязвимостей от Cloudflare (Security Audit Skill), TCB & Reference Monitor, headless security воркбенчи (HuntProxy) и агентные файрволы (Pipelock).*

| Заметка | Репозиторий | Звёзды | Теги |
| :--- | :--- | :--- | :--- |
| 📄 **[CL4R1T4S: База утекших системных промптов ведущих AI-моделей и агентов](05_security_osint_and_guardrails/CL4R1T4S.md)** | [elder-plinius/CL4R1T4S](https://github.com/elder-plinius/CL4R1T4S) | `48.4k+` | `#system-prompts` `#transparency` `#red-teaming` `#prompt-engineering` `#guardrails` `#ai-security` `#jailbreak-analysis` |
| 📄 **[AI/ML Pentesting Roadmap (2026 Edition): Руководство по тестированию на проникновение в LLM, Agentic AI, MCP и RAG](05_security_osint_and_guardrails/ai-ml-pentest-roadmap.md)** | [anmolksachan/AI-ML-Free-Resources-for-Security-and-Prompt-Injection](https://github.com/anmolksachan/AI-ML-Free-Resources-for-Security-and-Prompt-Injection) | `800+` | `#ai-ml-pentest` `#prompt-injection` `#agentic-security` `#mcp-security` `#rag-poisoning` `#owasp-llm` `#owasp-agentic` `#offensive-ai` `#red-teaming` `#bug-bounty` |
| 📄 **[API Relay Audit: Локальный аудит безопасности LLM-прокси, API-релеев и подмены моделей](05_security_osint_and_guardrails/api-relay-audit.md)** | [toby-bridges/api-relay-audit](https://github.com/toby-bridges/api-relay-audit) | `820+` | `#llm-security` `#api-proxy` `#audit` `#prompt-injection` `#model-substitution` `#sse-anomalies` `#tool-call-tampering` |
| 📄 **[APK-Reverse: Автоматизированный конвейер статического и динамического анализа безопасности Android APK](05_security_osint_and_guardrails/apk-reverse.md)** | [newliver666/apk-reverse](https://github.com/newliver666/apk-reverse) | `850+` | `#apk-reverse` `#android-security` `#reverse-engineering` `#decompilation` `#jadx` `#smali` `#static-analysis` `#secret-scanner` `#appsec` `#python` |
| 📄 **[ARTEX: Автономная AI-система этичного хакинга и пентестинга с Human-in-the-Loop контролем (Baidu Challenge Winner)](05_security_osint_and_guardrails/artex.md)** | [mhtsec/ARTEX](https://github.com/mhtsec/ARTEX) | `1.9k+` | `#artex` `#ai-pentesting` `#offensive-security` `#human-in-the-loop` `#scopesentry` `#mcp` `#attack-graph` `#traffic-evidence` `#go` `#nextjs` `#security-guardrails` |
| 📄 **[Claude-Red: Кураторская библиотека наступательных навыков (Offensive Security Skills) для Claude](05_security_osint_and_guardrails/claude-red.md)** | [SnailSploit/Claude-Red](https://github.com/SnailSploit/Claude-Red) | `3.7k+` | `#claude-skills` `#red-teaming` `#offensive-security` `#skill-md` `#prompt-engineering` `#pen-testing` `#exploit-development` `#edr-evasion` `#vulnerability-research` `#authorized-testing` |
| 📄 **[Coop: Изолированная микро-ВМ песочница от Trail of Bits для безопасного запуска Claude Code и Codex](05_security_osint_and_guardrails/coop.md)** | [trailofbits/coop](https://github.com/trailofbits/coop) | `560+` | `#coop` `#trailofbits` `#agent-sandbox` `#microvm` `#isolation` `#security` `#claude-code` `#codex` `#rust` `#appsec` |
| 📄 **[FQ-Book: Фундаментальная энциклопедия сетевых прокси, туннелей, VPN и механизмов цензуры GFW](05_security_osint_and_guardrails/fq-book.md)** | [hoochanlon/fq-book](https://github.com/hoochanlon/fq-book) | `6.8k+` | `#fq-book` `#network-security` `#proxy` `#vpn` `#shadowsocks` `#v2ray` `#gfw` `#tcp-rst` `#dns-poisoning` `#ipfs` `#anti-censorship` `#wireguard` |
| 📄 **[Ghost Security: Экосистема AI-Native AppSec инструментов и агентных MITM-прокси (Reaper, Poltergeist, Wraith)](05_security_osint_and_guardrails/ghost-security.md)** | [ghostsecurity](https://github.com/ghostsecurity) | `1.3k+ (всего)` | `#ghost-security` `#reaper` `#appsec` `#ai-agents` `#mitm-proxy` `#dast` `#sast` `#sca` `#mcp` `#claude-code` `#go` `#security-audit` |
| 📄 **[GPT-5.6 Instruct: Red Teaming и стресс-тестирование агентных систем](05_security_osint_and_guardrails/gpt-5.6-instruct.md)** | [MDX-Tom/gpt-5.6-instruct](https://github.com/MDX-Tom/gpt-5.6-instruct) | `7.1k+` | `#security` `#red-teaming` `#guardrails` `#alignment` `#jailbreak-testing` `#codex-cli` |
| 📄 **[HuntProxy: Headless перехватывающий веб-прокси и Security Workbench для AI-агентов на Rust](05_security_osint_and_guardrails/huntproxy.md)** | [BehiSecc/HuntProxy](https://github.com/BehiSecc/HuntProxy) | `175+` | `#huntproxy` `#rust` `#agent-proxy` `#mcp` `#security-workbench` `#burp-alternative` `#headless-browser` `#fuzzing` `#sitemap-discovery` `#web-security` `#ai-pentesting` |
| 📄 **[Анатомия ядра Linux и харденинг контейнеров: От Linux Insides до NCC Group](05_security_osint_and_guardrails/linux-kernel-and-container-hardening.md)** | [0xAX/linux-insides](https://github.com/0xAX/linux-insides) | `33.5k+` | `#linux-kernel` `#linux-insides` `#container-security` `#ncc-group` `#namespaces` `#cgroups` `#capabilities` `#seccomp-bpf` `#kernel-hardening` `#apparmor` `#selinux` `#sandboxing` |
| 📄 **[NVIDIA OpenShell: Официальный безопасный рантайм, изоляция системных вызовов и формальная верификация политик AI-агентов](05_security_osint_and_guardrails/openshell.md)** | [NVIDIA/OpenShell](https://github.com/NVIDIA/OpenShell) | `14.7k+` | `#openshell` `#nvidia` `#agent-runtime` `#sandboxing` `#kernel-security` `#formal-verification` `#reference-monitor` `#security-guardrails` `#kubernetes` `#rust` |
| 📄 **[Pipelock: Open-Source файрвол для AI-агентов, MCP-серверов и верифицируемого Egress-контроля](05_security_osint_and_guardrails/pipelock.md)** | [luckyPipewrench/pipelock](https://github.com/luckyPipewrench/pipelock) | `830+` | `#agent-firewall` `#egress-control` `#mcp-security` `#ssrf-prevention` `#prompt-injection` `#tcb` `#mediator-receipts` `#go` `#cncf` |
| 📄 **[Cloudflare Security Audit Skill: Шестифазный агентный аудит уязвимостей с верификацией](05_security_osint_and_guardrails/security-audit-skill.md)** | [cloudflare/security-audit-skill](https://github.com/cloudflare/security-audit-skill) | `4.6k+` | `#security-audit-skill` `#cloudflare` `#agent-skills` `#vulnerability-assessment` `#security-audit` `#sarif` `#json-findings` `#prompt-injection` `#claude-code` `#adversarial-verification` `#sandboxing` |
| 📄 **[SkillSpector: Сканер безопасности и Supply-Chain аудитор агентных навыков (NVIDIA)](05_security_osint_and_guardrails/skillspector.md)** | [NVIDIA/SkillSpector](https://github.com/NVIDIA/SkillSpector) | `16.1k+` | `#agent-security` `#supply-chain` `#skill-scanner` `#prompt-injection` `#claude-code` `#mcp` `#nvidia` `#static-analysis` |
| 📄 **[Smokescreen: HTTP CONNECT прокси от Stripe для изоляции Egress-трафика и защиты от SSRF](05_security_osint_and_guardrails/smokescreen.md)** | [stripe/smokescreen](https://github.com/stripe/smokescreen) | `1.3k+` | `#egress-proxy` `#ssrf-prevention` `#stripe` `#go` `#network-security` `#tcb` `#dns-rebinding` `#acl` |
| 📄 **[TCB & Reference Monitor: Полное руководство по архитектуре доверенной базы вычислений для автономных AI-агентов](05_security_osint_and_guardrails/tcb-agent-security.md)** | [ai_pentester/tcb](local://ai_pentester/tcb) | `Master-Architecture` | `#tcb` `#trusted-computing-base` `#reference-monitor` `#agent-security` `#fail-closed` `#ssrf-prevention` `#prompt-injection` `#zero-trust` `#sandboxing` `#secret-broker` |
| 📄 **[User Scanner: Профессиональный OSINT-комбайн по Email и Никнеймам](05_security_osint_and_guardrails/user-scanner.md)** | [kaifcodec/user-scanner](https://github.com/kaifcodec/user-scanner) | `4.5k+` | `#osint` `#security` `#digital-footprint` `#email-recon` `#username-scanner` `#python` |

### ⚡ 06. Инструменты разработчика, архитектура и нативный софт
*Сверхлегкие headless-браузеры на чистом Rust для AI-агентов (Moli), сетевой MITM-анализ затрат контекста LLM (cost-xray), визуальное архитектурное код-ревью AI-генераций (Whiteboard), сверхбыстрые дисковые анализаторы на Rust и GPUI (Disktree Тоби Лютке), курирование мирового Open Source (RuanYF Weekly), распределенные S3 хранилища на Rust (RustFS), браузерная автоматизация (Tencent BrowserSkill), системный дизайн (System Design 101) и краулеры для LLM (Crawl4AI).*

| Заметка | Репозиторий | Звёзды | Теги |
| :--- | :--- | :--- | :--- |
| 📄 **[AIHawk: Скрытный антибот-браузер и агент веб-автоматизации с поддержкой MCP (Undetected Browsing)](06_developer_tools_and_apps/ai-hawk.md)** | [feder-cr/AIHawk](https://github.com/feder-cr/AIHawk) | `31.5k+` | `#ai-hawk` `#stealth-browser` `#anti-detect` `#anti-bot-bypass` `#mcp` `#browser-agent` `#web-automation` `#computer-use` `#playwright` `#cloudflare-bypass` `#python` |
| 📄 **[Tencent BrowserSkill: Агентная автоматизация реального браузера без перехвата фокуса (Rust + Chromium Extension)](06_developer_tools_and_apps/browserskill.md)** | [Tencent/BrowserSkill](https://github.com/Tencent/BrowserSkill) | `2.8k+` | `#browserskill` `#tencent` `#browser-automation` `#browser-agent` `#rust` `#bsk-cli` `#chromium-extension` `#human-in-the-loop` `#tab-borrowing` `#claude-code` `#cursor` |
| 📄 **[cost-xray: Прозрачный сетевой инспектор и покомпонентная атрибуция расходов контекста кодинг-агентов](06_developer_tools_and_apps/cost-xray.md)** | [tigerless-labs/cost-xray](https://github.com/tigerless-labs/cost-xray) | `2.3k+` | `#cost-xray` `#claude-code` `#codex` `#token-inspector` `#cost-analysis` `#mitmproxy` `#devtools` `#mcp` `#prompt-engineering` |
| 📄 **[Crawl4AI: Высокопроизводительный открытый веб-краулер и парсер для LLM, RAG и AI-агентов](06_developer_tools_and_apps/crawl4ai.md)** | [unclecode/crawl4ai](https://github.com/unclecode/crawl4ai) | `82.8k+` | `#crawl4ai` `#web-crawler` `#web-scraping` `#llm-ready` `#markdown` `#rag` `#ai-agents` `#playwright` `#structured-extraction` `#bm25` `#docker` |
| 📄 **[Disktree: Сверхбыстрый визуализатор дискового пространства на Rust и движке GPUI от Тоби Лютке](06_developer_tools_and_apps/disktree.md)** | [tobi/disktree](https://github.com/tobi/disktree) | `660+` | `#disktree` `#tobi-lutke` `#rust` `#gpui` `#zed` `#disk-analyzer` `#treemap` `#system-tools` `#high-performance` |
| 📄 **[Fastpotify: Нативный и молниеносный клиент Spotify на Rust](06_developer_tools_and_apps/fastpotify.md)** | [crmne/fastpotify](https://github.com/crmne/fastpotify) | `1.3k+` | `#rust` `#desktop-app` `#spotify` `#egui` `#librespot` `#audio-player` |
| 📄 **[Moli: Сверхлегкий headless-браузер на чистом Rust для AI-агентов (Structure First, Pixels on Demand)](06_developer_tools_and_apps/moli.md)** | [lexmount/moli](https://github.com/lexmount/moli) | `6.8k+` | `#moli` `#headless-browser` `#rust` `#ai-agents` `#browser-automation` `#cdp` `#webdriver-bidi` `#playwright` `#web-scraping` `#dom-first` |
| 📄 **[Obscura: Высокопроизводительный Headless-Браузер для AI-Агентов на Rust](06_developer_tools_and_apps/obscura.md)** | [h4ckf0r0day/obscura](https://github.com/h4ckf0r0day/obscura) | `23.3k+` | `#headless-browser` `#rust` `#anti-bot-bypass` `#accessibility-tree` `#web-scraping` |
| 📄 **[RuanYF Weekly: Инженерный феномен технологического дайджеста открытого ПО (104k+ ★)](06_developer_tools_and_apps/ruanyf-weekly.md)** | [ruanyf/weekly](https://github.com/ruanyf/weekly) | `104k+` | `#ruanyf-weekly` `#tech-digest` `#open-source-curation` `#developer-tools` `#engineering-ecosystem` `#curated-list` `#community-driven` |
| 📄 **[RustFS: Высокопроизводительное распределенное S3-совместимое объектное хранилище на Rust](06_developer_tools_and_apps/rustfs.md)** | [rustfs/rustfs](https://github.com/rustfs/rustfs) | `33.0k+` | `#rustfs` `#object-storage` `#s3-compatible` `#rust` `#distributed-systems` `#minio-alternative` `#iceberg` `#storage-engine` `#high-performance` |
| 📄 **[System Design 101: Визуальная энциклопедия архитектуры распределенных систем (ByteByteGo)](06_developer_tools_and_apps/system-design-101.md)** | [ByteByteGoHq/system-design-101](https://github.com/ByteByteGoHq/system-design-101) | `88.6k+` | `#system-design` `#distributed-systems` `#architecture` `#microservices` `#databases` `#caching` `#bytebytego` `#visual-guide` |
| 📄 **[Whiteboard: Интерактивный архитектурный холст для визуального код-ревью AI-генераций](06_developer_tools_and_apps/whiteboard.md)** | [devdotfast/whiteboard](https://github.com/devdotfast/whiteboard) | `1.1k+` | `#whiteboard` `#ai-code-review` `#code-diff` `#visual-architecture` `#pull-requests` `#claude-code` `#cursor` `#typescript` `#devtools` |

---

## 🏷️ Облако тегов (Tag Index)

* **`#aacr-bench`** (1): [Open Code Review](02_agent_runtimes_and_harnesses/open-code-review.md)
* **`#academic-research`** (2): [Academic Research Skills](04_scientific_research_and_discovery/academic-research-skills.md), [Hyperresearch](04_scientific_research_and_discovery/hyperresearch.md)
* **`#accessibility-api`** (1): [Jev-Chat Jarvis](02_agent_runtimes_and_harnesses/jev-chat-jarvis.md)
* **`#accessibility-tree`** (1): [Obscura](06_developer_tools_and_apps/obscura.md)
* **`#acl`** (1): [Smokescreen](05_security_osint_and_guardrails/smokescreen.md)
* **`#action-execution`** (1): [Evenfire](02_agent_runtimes_and_harnesses/evenfire.md)
* **`#action-fusion`** (1): [SoL-Pi](02_agent_runtimes_and_harnesses/sol-pi.md)
* **`#active-learning`** (1): [VibeWise](02_agent_runtimes_and_harnesses/vibe-wise.md)
* **`#adhd`** (1): [i-have-adhd](02_agent_runtimes_and_harnesses/i-have-adhd.md)
* **`#adversarial-verification`** (1): [Cloudflare Security Audit Skill](05_security_osint_and_guardrails/security-audit-skill.md)
* **`#agent-architecture`** (1): [Learn Harness Engineering (Курс WalkingLabs](02_agent_runtimes_and_harnesses/learn-harness-engineering.md)
* **`#agent-evals`** (1): [AI Agent Book](02_agent_runtimes_and_harnesses/ai-agent-book.md)
* **`#agent-eyes`** (1): [Agent-Reach](02_agent_runtimes_and_harnesses/agent-reach.md)
* **`#agent-firewall`** (1): [Pipelock](05_security_osint_and_guardrails/pipelock.md)
* **`#agent-harness`** (3): [AutoHarness](02_agent_runtimes_and_harnesses/autoharness.md), [Jev Ultrafast](02_agent_runtimes_and_harnesses/jev-ultrafast.md), [SoL-Pi](02_agent_runtimes_and_harnesses/sol-pi.md)
* **`#agent-hybrid`** (1): [Open Code Review](02_agent_runtimes_and_harnesses/open-code-review.md)
* **`#agent-memory`** (3): [AI-Memory](02_agent_runtimes_and_harnesses/ai-memory.md), [Hindsight](02_agent_runtimes_and_harnesses/hindsight.md), [Reef](02_agent_runtimes_and_harnesses/reef.md)
* **`#agent-orchestration`** (3): [AI Engineering from Scratch (Рохит Гумаре](01_llm_architecture_and_training/ai-engineering-from-scratch.md), [Google AX](02_agent_runtimes_and_harnesses/google-ax.md), [Paperclip](02_agent_runtimes_and_harnesses/paperclip.md)
* **`#agent-passport`** (1): [Docker Agent](02_agent_runtimes_and_harnesses/docker-agent.md)
* **`#agent-proxy`** (1): [HuntProxy](05_security_osint_and_guardrails/huntproxy.md)
* **`#agent-reach`** (1): [Agent-Reach](02_agent_runtimes_and_harnesses/agent-reach.md)
* **`#agent-runtime`** (4): [Evenfire](02_agent_runtimes_and_harnesses/evenfire.md), [Архитектура Tool Broker & Execution Blocker](02_agent_runtimes_and_harnesses/tool-broker-architecture.md), [Univer](02_agent_runtimes_and_harnesses/univer.md), [NVIDIA OpenShell](05_security_osint_and_guardrails/openshell.md)
* **`#agent-sandbox`** (4): [Dormice](02_agent_runtimes_and_harnesses/dormice.md), [Monty](02_agent_runtimes_and_harnesses/monty.md), [ZeroBoot](02_agent_runtimes_and_harnesses/zeroboot.md), [Coop](05_security_osint_and_guardrails/coop.md)
* **`#agent-security`** (3): [ArcBox](02_agent_runtimes_and_harnesses/arcbox.md), [SkillSpector](05_security_osint_and_guardrails/skillspector.md), [TCB & Reference Monitor](05_security_osint_and_guardrails/tcb-agent-security.md)
* **`#agent-skill`** (1): [Answer Me with HTML](02_agent_runtimes_and_harnesses/answer-me-with-html.md)
* **`#agent-skills`** (6): [Agent-Skills](02_agent_runtimes_and_harnesses/agent-skills.md), [Claude Knowledge Work Plugins](02_agent_runtimes_and_harnesses/claude-knowledge-work-plugins.md), [i-have-adhd](02_agent_runtimes_and_harnesses/i-have-adhd.md), [Ponytail](02_agent_runtimes_and_harnesses/ponytail.md), [Scientific Agent Skills (K-Dense AI](04_scientific_research_and_discovery/scientific-agent-skills.md), [Cloudflare Security Audit Skill](05_security_osint_and_guardrails/security-audit-skill.md)
* **`#agent-substrate`** (1): [Google AX](02_agent_runtimes_and_harnesses/google-ax.md)
* **`#agent-to-agent`** (1): [EnvoyMesh](02_agent_runtimes_and_harnesses/envoymesh.md)
* **`#agent-workforce`** (1): [Paperclip](02_agent_runtimes_and_harnesses/paperclip.md)
* **`#agent-workspace`** (1): [OpenDots](02_agent_runtimes_and_harnesses/opendots.md)
* **`#agentic-security`** (1): [AI/ML Pentesting Roadmap (2026 Edition)](05_security_osint_and_guardrails/ai-ml-pentest-roadmap.md)
* **`#agents`** (1): [Hyperresearch](04_scientific_research_and_discovery/hyperresearch.md)
* **`#ai-agent`** (1): [Hindsight](02_agent_runtimes_and_harnesses/hindsight.md)
* **`#ai-agent-book`** (1): [AI Agent Book](02_agent_runtimes_and_harnesses/ai-agent-book.md)
* **`#ai-agents`** (8): [LLM-Master](01_llm_architecture_and_training/llm-master.md), [Atlas](02_agent_runtimes_and_harnesses/atlas.md), [Diagram Design](02_agent_runtimes_and_harnesses/diagram-design.md), [Learn Harness Engineering (Курс WalkingLabs](02_agent_runtimes_and_harnesses/learn-harness-engineering.md), [zvec-grep (zg)](02_agent_runtimes_and_harnesses/zvec-grep.md), [Ghost Security](05_security_osint_and_guardrails/ghost-security.md), [Crawl4AI](06_developer_tools_and_apps/crawl4ai.md), [Moli](06_developer_tools_and_apps/moli.md)
* **`#ai-code-review`** (1): [Whiteboard](06_developer_tools_and_apps/whiteboard.md)
* **`#ai-coding`** (3): [AI-Memory](02_agent_runtimes_and_harnesses/ai-memory.md), [Awesome DESIGN.md](02_agent_runtimes_and_harnesses/awesome-design-md.md), [M3E Canvas](02_agent_runtimes_and_harnesses/m3e-canvas.md)
* **`#ai-coworkers`** (1): [OpenDots](02_agent_runtimes_and_harnesses/opendots.md)
* **`#ai-engineering`** (4): [AI Engineering Interviews](00_strategy_and_roadmaps/ai-engineering-interviews.md), [Capstone Roadmap](00_strategy_and_roadmaps/capstone-engineering-roadmap.md), [Up (人生进阶指南)](00_strategy_and_roadmaps/up.md), [AI Engineering from Scratch (Рохит Гумаре](01_llm_architecture_and_training/ai-engineering-from-scratch.md)
* **`#ai-gateway`** (1): [Magpie](02_agent_runtimes_and_harnesses/magpie.md)
* **`#ai-hawk`** (1): [AIHawk](06_developer_tools_and_apps/ai-hawk.md)
* **`#ai-infra-book`** (1): [AI Infra Book](01_llm_architecture_and_training/ai-infra-book.md)
* **`#ai-infrastructure`** (1): [AI Infra Book](01_llm_architecture_and_training/ai-infra-book.md)
* **`#ai-memory`** (1): [AI-Memory](02_agent_runtimes_and_harnesses/ai-memory.md)
* **`#ai-ml-pentest`** (1): [AI/ML Pentesting Roadmap (2026 Edition)](05_security_osint_and_guardrails/ai-ml-pentest-roadmap.md)
* **`#ai-pentesting`** (2): [ARTEX](05_security_osint_and_guardrails/artex.md), [HuntProxy](05_security_osint_and_guardrails/huntproxy.md)
* **`#ai-science`** (1): [Scientific Agent Skills (K-Dense AI](04_scientific_research_and_discovery/scientific-agent-skills.md)
* **`#ai-security`** (1): [CL4R1T4S](05_security_osint_and_guardrails/CL4R1T4S.md)
* **`#alex-xu`** (1): [System Design Notes](00_strategy_and_roadmaps/system-design-notes.md)
* **`#alibaba`** (1): [Open Code Review](02_agent_runtimes_and_harnesses/open-code-review.md)
* **`#alignment`** (1): [GPT-5.6 Instruct](05_security_osint_and_guardrails/gpt-5.6-instruct.md)
* **`#alphafold`** (1): [Scientific Agent Skills (K-Dense AI](04_scientific_research_and_discovery/scientific-agent-skills.md)
* **`#alphaxiv`** (1): [alphaXiv OpenResearch](04_scientific_research_and_discovery/openresearch.md)
* **`#android`** (1): [Jev-Chat Jarvis](02_agent_runtimes_and_harnesses/jev-chat-jarvis.md)
* **`#android-security`** (1): [APK-Reverse](05_security_osint_and_guardrails/apk-reverse.md)
* **`#answer-me-with-html`** (1): [Answer Me with HTML](02_agent_runtimes_and_harnesses/answer-me-with-html.md)
* **`#anthropic`** (1): [Claude Knowledge Work Plugins](02_agent_runtimes_and_harnesses/claude-knowledge-work-plugins.md)
* **`#anti-bot-bypass`** (2): [AIHawk](06_developer_tools_and_apps/ai-hawk.md), [Obscura](06_developer_tools_and_apps/obscura.md)
* **`#anti-censorship`** (1): [FQ-Book](05_security_osint_and_guardrails/fq-book.md)
* **`#anti-detect`** (1): [AIHawk](06_developer_tools_and_apps/ai-hawk.md)
* **`#antigravity`** (1): [Agent-Skills](02_agent_runtimes_and_harnesses/agent-skills.md)
* **`#api-gateway`** (1): [Evenfire](02_agent_runtimes_and_harnesses/evenfire.md)
* **`#api-proxy`** (1): [API Relay Audit](05_security_osint_and_guardrails/api-relay-audit.md)
* **`#apk-reverse`** (1): [APK-Reverse](05_security_osint_and_guardrails/apk-reverse.md)
* **`#apparmor`** (1): [Анатомия ядра Linux и харденинг контейнеров](05_security_osint_and_guardrails/linux-kernel-and-container-hardening.md)
* **`#apple-silicon`** (1): [Kev](01_llm_architecture_and_training/kev.md)
* **`#appsec`** (3): [APK-Reverse](05_security_osint_and_guardrails/apk-reverse.md), [Coop](05_security_osint_and_guardrails/coop.md), [Ghost Security](05_security_osint_and_guardrails/ghost-security.md)
* **`#architecture`** (2): [System Design Notes](00_strategy_and_roadmaps/system-design-notes.md), [System Design 101](06_developer_tools_and_apps/system-design-101.md)
* **`#artex`** (1): [ARTEX](05_security_osint_and_guardrails/artex.md)
* **`#arxiv`** (3): [Hindsight](02_agent_runtimes_and_harnesses/hindsight.md), [alphaXiv OpenResearch](04_scientific_research_and_discovery/openresearch.md), [PRAXIST](04_scientific_research_and_discovery/praxist.md)
* **`#ast-analysis`** (1): [Open Code Review](02_agent_runtimes_and_harnesses/open-code-review.md)
* **`#ast-merge`** (1): [Atlas](02_agent_runtimes_and_harnesses/atlas.md)
* **`#attack-graph`** (1): [ARTEX](05_security_osint_and_guardrails/artex.md)
* **`#audio-player`** (1): [Fastpotify](06_developer_tools_and_apps/fastpotify.md)
* **`#audit`** (1): [API Relay Audit](05_security_osint_and_guardrails/api-relay-audit.md)
* **`#audit-harness`** (1): [Learn Harness Engineering (Курс WalkingLabs](02_agent_runtimes_and_harnesses/learn-harness-engineering.md)
* **`#authorized-testing`** (1): [Claude-Red](05_security_osint_and_guardrails/claude-red.md)
* **`#auto-research`** (1): [SoL-Pi](02_agent_runtimes_and_harnesses/sol-pi.md)
* **`#autoharness`** (1): [AutoHarness](02_agent_runtimes_and_harnesses/autoharness.md)
* **`#autonomous-agents`** (1): [OpenDots](02_agent_runtimes_and_harnesses/opendots.md)
* **`#autonomous-research`** (2): [Capstone Roadmap](00_strategy_and_roadmaps/capstone-engineering-roadmap.md), [PRAXIST](04_scientific_research_and_discovery/praxist.md)
* **`#autoresearch`** (1): [alphaXiv OpenResearch](04_scientific_research_and_discovery/openresearch.md)
* **`#awesome-jev`** (1): [Awesome-Jev](02_agent_runtimes_and_harnesses/awesome-jev.md)
* **`#bilibili`** (1): [Agent-Reach](02_agent_runtimes_and_harnesses/agent-reach.md)
* **`#biology`** (1): [Scientific Agent Skills (K-Dense AI](04_scientific_research_and_discovery/scientific-agent-skills.md)
* **`#bm25`** (2): [zvec-grep (zg)](02_agent_runtimes_and_harnesses/zvec-grep.md), [Crawl4AI](06_developer_tools_and_apps/crawl4ai.md)
* **`#bojie-li`** (2): [AI Infra Book](01_llm_architecture_and_training/ai-infra-book.md), [AI Agent Book](02_agent_runtimes_and_harnesses/ai-agent-book.md)
* **`#browser-agent`** (3): [Jev Ultrafast](02_agent_runtimes_and_harnesses/jev-ultrafast.md), [AIHawk](06_developer_tools_and_apps/ai-hawk.md), [Tencent BrowserSkill](06_developer_tools_and_apps/browserskill.md)
* **`#browser-agents`** (1): [Awesome-Jev](02_agent_runtimes_and_harnesses/awesome-jev.md)
* **`#browser-automation`** (2): [Tencent BrowserSkill](06_developer_tools_and_apps/browserskill.md), [Moli](06_developer_tools_and_apps/moli.md)
* **`#browser-use`** (1): [Jev Ultrafast](02_agent_runtimes_and_harnesses/jev-ultrafast.md)
* **`#browserskill`** (1): [Tencent BrowserSkill](06_developer_tools_and_apps/browserskill.md)
* **`#bsk-cli`** (1): [Tencent BrowserSkill](06_developer_tools_and_apps/browserskill.md)
* **`#bug-bounty`** (1): [AI/ML Pentesting Roadmap (2026 Edition)](05_security_osint_and_guardrails/ai-ml-pentest-roadmap.md)
* **`#burp-alternative`** (1): [HuntProxy](05_security_osint_and_guardrails/huntproxy.md)
* **`#bytebytego`** (2): [System Design Notes](00_strategy_and_roadmaps/system-design-notes.md), [System Design 101](06_developer_tools_and_apps/system-design-101.md)
* **`#caching`** (1): [System Design 101](06_developer_tools_and_apps/system-design-101.md)
* **`#canvas`** (2): [M3E Canvas](02_agent_runtimes_and_harnesses/m3e-canvas.md), [Univer](02_agent_runtimes_and_harnesses/univer.md)
* **`#capabilities`** (1): [Анатомия ядра Linux и харденинг контейнеров](05_security_osint_and_guardrails/linux-kernel-and-container-hardening.md)
* **`#capstone-project`** (1): [Capstone Roadmap](00_strategy_and_roadmaps/capstone-engineering-roadmap.md)
* **`#career-roadmap`** (2): [AI Engineering Interviews](00_strategy_and_roadmaps/ai-engineering-interviews.md), [Up (人生进阶指南)](00_strategy_and_roadmaps/up.md)
* **`#catalog`** (1): [Awesome-Jev](02_agent_runtimes_and_harnesses/awesome-jev.md)
* **`#catastrophic-forgetting`** (1): [Reef](02_agent_runtimes_and_harnesses/reef.md)
* **`#cdp`** (1): [Moli](06_developer_tools_and_apps/moli.md)
* **`#cgroups`** (1): [Анатомия ядра Linux и харденинг контейнеров](05_security_osint_and_guardrails/linux-kernel-and-container-hardening.md)
* **`#chat-copilot`** (1): [Jev-Chat Jarvis](02_agent_runtimes_and_harnesses/jev-chat-jarvis.md)
* **`#chemistry`** (1): [Scientific Agent Skills (K-Dense AI](04_scientific_research_and_discovery/scientific-agent-skills.md)
* **`#chromium-extension`** (1): [Tencent BrowserSkill](06_developer_tools_and_apps/browserskill.md)
* **`#citation-audit`** (1): [Academic Research Skills](04_scientific_research_and_discovery/academic-research-skills.md)
* **`#citation-verification`** (1): [Hyperresearch](04_scientific_research_and_discovery/hyperresearch.md)
* **`#claude-code`** (23): [Agent-Skills](02_agent_runtimes_and_harnesses/agent-skills.md), [AI-Memory](02_agent_runtimes_and_harnesses/ai-memory.md), [Answer Me with HTML](02_agent_runtimes_and_harnesses/answer-me-with-html.md), [AutoHarness](02_agent_runtimes_and_harnesses/autoharness.md), [Awesome DESIGN.md](02_agent_runtimes_and_harnesses/awesome-design-md.md), [Claude Knowledge Work Plugins](02_agent_runtimes_and_harnesses/claude-knowledge-work-plugins.md), [Diagram Design](02_agent_runtimes_and_harnesses/diagram-design.md), [i-have-adhd](02_agent_runtimes_and_harnesses/i-have-adhd.md), [Impeccable](02_agent_runtimes_and_harnesses/impeccable.md), [Magpie](02_agent_runtimes_and_harnesses/magpie.md), [OpenSpec](02_agent_runtimes_and_harnesses/openspec.md), [Ponytail](02_agent_runtimes_and_harnesses/ponytail.md), [VibeWise](02_agent_runtimes_and_harnesses/vibe-wise.md), [Academic Research Skills](04_scientific_research_and_discovery/academic-research-skills.md), [Hyperresearch](04_scientific_research_and_discovery/hyperresearch.md), [alphaXiv OpenResearch](04_scientific_research_and_discovery/openresearch.md), [Coop](05_security_osint_and_guardrails/coop.md), [Ghost Security](05_security_osint_and_guardrails/ghost-security.md), [Cloudflare Security Audit Skill](05_security_osint_and_guardrails/security-audit-skill.md), [SkillSpector](05_security_osint_and_guardrails/skillspector.md), [Tencent BrowserSkill](06_developer_tools_and_apps/browserskill.md), [cost-xray](06_developer_tools_and_apps/cost-xray.md), [Whiteboard](06_developer_tools_and_apps/whiteboard.md)
* **`#claude-cowork`** (1): [Claude Knowledge Work Plugins](02_agent_runtimes_and_harnesses/claude-knowledge-work-plugins.md)
* **`#claude-plugin`** (1): [VibeWise](02_agent_runtimes_and_harnesses/vibe-wise.md)
* **`#claude-plugins`** (1): [Claude Knowledge Work Plugins](02_agent_runtimes_and_harnesses/claude-knowledge-work-plugins.md)
* **`#claude-skills`** (1): [Claude-Red](05_security_osint_and_guardrails/claude-red.md)
* **`#clm`** (1): [CLM](01_llm_architecture_and_training/clm.md)
* **`#cloudflare`** (1): [Cloudflare Security Audit Skill](05_security_osint_and_guardrails/security-audit-skill.md)
* **`#cloudflare-bypass`** (1): [AIHawk](06_developer_tools_and_apps/ai-hawk.md)
* **`#cluster-runtime`** (1): [Google AX](02_agent_runtimes_and_harnesses/google-ax.md)
* **`#cncf`** (1): [Pipelock](05_security_osint_and_guardrails/pipelock.md)
* **`#code-diff`** (1): [Whiteboard](06_developer_tools_and_apps/whiteboard.md)
* **`#code-execution`** (1): [ZeroBoot](02_agent_runtimes_and_harnesses/zeroboot.md)
* **`#code-mode`** (1): [Monty](02_agent_runtimes_and_harnesses/monty.md)
* **`#code-reduction`** (1): [Ponytail](02_agent_runtimes_and_harnesses/ponytail.md)
* **`#code-review`** (1): [Open Code Review](02_agent_runtimes_and_harnesses/open-code-review.md)
* **`#code-search`** (1): [zvec-grep (zg)](02_agent_runtimes_and_harnesses/zvec-grep.md)
* **`#codex`** (9): [AI-Memory](02_agent_runtimes_and_harnesses/ai-memory.md), [Answer Me with HTML](02_agent_runtimes_and_harnesses/answer-me-with-html.md), [Awesome DESIGN.md](02_agent_runtimes_and_harnesses/awesome-design-md.md), [Diagram Design](02_agent_runtimes_and_harnesses/diagram-design.md), [i-have-adhd](02_agent_runtimes_and_harnesses/i-have-adhd.md), [Impeccable](02_agent_runtimes_and_harnesses/impeccable.md), [Magpie](02_agent_runtimes_and_harnesses/magpie.md), [Coop](05_security_osint_and_guardrails/coop.md), [cost-xray](06_developer_tools_and_apps/cost-xray.md)
* **`#codex-cli`** (1): [GPT-5.6 Instruct](05_security_osint_and_guardrails/gpt-5.6-instruct.md)
* **`#coding-agents`** (2): [AI Agent Book](02_agent_runtimes_and_harnesses/ai-agent-book.md), [OpenSpec](02_agent_runtimes_and_harnesses/openspec.md)
* **`#community-driven`** (1): [RuanYF Weekly](06_developer_tools_and_apps/ruanyf-weekly.md)
* **`#computer-use`** (1): [AIHawk](06_developer_tools_and_apps/ai-hawk.md)
* **`#container-security`** (1): [Анатомия ядра Linux и харденинг контейнеров](05_security_osint_and_guardrails/linux-kernel-and-container-hardening.md)
* **`#containers`** (1): [ArcBox](02_agent_runtimes_and_harnesses/arcbox.md)
* **`#context-compression`** (1): [SoL-Pi](02_agent_runtimes_and_harnesses/sol-pi.md)
* **`#context-engineering`** (2): [AI Agent Book](02_agent_runtimes_and_harnesses/ai-agent-book.md), [OpenSpec](02_agent_runtimes_and_harnesses/openspec.md)
* **`#context-handoff`** (1): [AI-Memory](02_agent_runtimes_and_harnesses/ai-memory.md)
* **`#continual-learning`** (3): [AutoHarness](02_agent_runtimes_and_harnesses/autoharness.md), [Hindsight](02_agent_runtimes_and_harnesses/hindsight.md), [Reef](02_agent_runtimes_and_harnesses/reef.md)
* **`#continuous-evolution`** (1): [AI Agent Book](02_agent_runtimes_and_harnesses/ai-agent-book.md)
* **`#contrastive-learning`** (1): [CLM](01_llm_architecture_and_training/clm.md)
* **`#coop`** (1): [Coop](05_security_osint_and_guardrails/coop.md)
* **`#copilotkit`** (1): [OpenDots](02_agent_runtimes_and_harnesses/opendots.md)
* **`#copy-on-write`** (1): [ZeroBoot](02_agent_runtimes_and_harnesses/zeroboot.md)
* **`#core-bench`** (1): [AutoHarness](02_agent_runtimes_and_harnesses/autoharness.md)
* **`#cost-analysis`** (1): [cost-xray](06_developer_tools_and_apps/cost-xray.md)
* **`#cost-optimization`** (1): [Magpie](02_agent_runtimes_and_harnesses/magpie.md)
* **`#cost-xray`** (1): [cost-xray](06_developer_tools_and_apps/cost-xray.md)
* **`#crawl4ai`** (1): [Crawl4AI](06_developer_tools_and_apps/crawl4ai.md)
* **`#credential-offloading`** (1): [Архитектура Tool Broker & Execution Blocker](02_agent_runtimes_and_harnesses/tool-broker-architecture.md)
* **`#curated-list`** (3): [AI Engineering Interviews](00_strategy_and_roadmaps/ai-engineering-interviews.md), [Awesome-Jev](02_agent_runtimes_and_harnesses/awesome-jev.md), [RuanYF Weekly](06_developer_tools_and_apps/ruanyf-weekly.md)
* **`#cursor`** (11): [Agent-Skills](02_agent_runtimes_and_harnesses/agent-skills.md), [AI-Memory](02_agent_runtimes_and_harnesses/ai-memory.md), [Answer Me with HTML](02_agent_runtimes_and_harnesses/answer-me-with-html.md), [Awesome DESIGN.md](02_agent_runtimes_and_harnesses/awesome-design-md.md), [i-have-adhd](02_agent_runtimes_and_harnesses/i-have-adhd.md), [Impeccable](02_agent_runtimes_and_harnesses/impeccable.md), [OpenSpec](02_agent_runtimes_and_harnesses/openspec.md), [Ponytail](02_agent_runtimes_and_harnesses/ponytail.md), [alphaXiv OpenResearch](04_scientific_research_and_discovery/openresearch.md), [Tencent BrowserSkill](06_developer_tools_and_apps/browserskill.md), [Whiteboard](06_developer_tools_and_apps/whiteboard.md)
* **`#dast`** (1): [Ghost Security](05_security_osint_and_guardrails/ghost-security.md)
* **`#data-visualization`** (2): [Answer Me with HTML](02_agent_runtimes_and_harnesses/answer-me-with-html.md), [Diagram Design](02_agent_runtimes_and_harnesses/diagram-design.md)
* **`#database-sharding`** (1): [System Design Notes](00_strategy_and_roadmaps/system-design-notes.md)
* **`#databases`** (1): [System Design 101](06_developer_tools_and_apps/system-design-101.md)
* **`#datalog`** (1): [Semantica AGI](03_knowledge_graphs_and_ontologies/semantica.md)
* **`#decentralized-agents`** (1): [EnvoyMesh](02_agent_runtimes_and_harnesses/envoymesh.md)
* **`#decision-engine`** (1): [Awesome-Jev](02_agent_runtimes_and_harnesses/awesome-jev.md)
* **`#decision-intelligence`** (1): [Semantica AGI](03_knowledge_graphs_and_ontologies/semantica.md)
* **`#decision-making`** (1): [OpenJev](01_llm_architecture_and_training/openjev.md)
* **`#declarative-workflows`** (1): [Google AX](02_agent_runtimes_and_harnesses/google-ax.md)
* **`#decompilation`** (1): [APK-Reverse](05_security_osint_and_guardrails/apk-reverse.md)
* **`#deep-learning`** (2): [LLMs from Scratch (Себастьян Рашка)](01_llm_architecture_and_training/LLMs-from-scratch.md), [Dive into LLMs (动手学大模型)](01_llm_architecture_and_training/dive-into-llms.md)
* **`#deep-research`** (1): [Hyperresearch](04_scientific_research_and_discovery/hyperresearch.md)
* **`#deepseek-r1`** (1): [Reasoning from Scratch (Себастьян Рашка](01_llm_architecture_and_training/reasoning-from-scratch.md)
* **`#design-quality`** (1): [Impeccable](02_agent_runtimes_and_harnesses/impeccable.md)
* **`#design-system`** (1): [Impeccable](02_agent_runtimes_and_harnesses/impeccable.md)
* **`#design-systems`** (1): [Awesome DESIGN.md](02_agent_runtimes_and_harnesses/awesome-design-md.md)
* **`#desktop-app`** (1): [Fastpotify](06_developer_tools_and_apps/fastpotify.md)
* **`#deterministic-engineering`** (1): [Open Code Review](02_agent_runtimes_and_harnesses/open-code-review.md)
* **`#developer-tools`** (1): [RuanYF Weekly](06_developer_tools_and_apps/ruanyf-weekly.md)
* **`#devtools`** (2): [cost-xray](06_developer_tools_and_apps/cost-xray.md), [Whiteboard](06_developer_tools_and_apps/whiteboard.md)
* **`#diagrams`** (1): [Diagram Design](02_agent_runtimes_and_harnesses/diagram-design.md)
* **`#digital-footprint`** (1): [User Scanner](05_security_osint_and_guardrails/user-scanner.md)
* **`#direct-logits`** (2): [Laya](01_llm_architecture_and_training/laya.md), [OpenJev](01_llm_architecture_and_training/openjev.md)
* **`#disk-analyzer`** (1): [Disktree](06_developer_tools_and_apps/disktree.md)
* **`#disktree`** (1): [Disktree](06_developer_tools_and_apps/disktree.md)
* **`#distributed-inference`** (1): [AI Infra Book](01_llm_architecture_and_training/ai-infra-book.md)
* **`#distributed-systems`** (3): [System Design Notes](00_strategy_and_roadmaps/system-design-notes.md), [RustFS](06_developer_tools_and_apps/rustfs.md), [System Design 101](06_developer_tools_and_apps/system-design-101.md)
* **`#distributed-training`** (1): [AI Infra Book](01_llm_architecture_and_training/ai-infra-book.md)
* **`#dns-poisoning`** (1): [FQ-Book](05_security_osint_and_guardrails/fq-book.md)
* **`#dns-rebinding`** (1): [Smokescreen](05_security_osint_and_guardrails/smokescreen.md)
* **`#docker`** (2): [Dormice](02_agent_runtimes_and_harnesses/dormice.md), [Crawl4AI](06_developer_tools_and_apps/crawl4ai.md)
* **`#docker-agent`** (1): [Docker Agent](02_agent_runtimes_and_harnesses/docker-agent.md)
* **`#docs`** (1): [Univer](02_agent_runtimes_and_harnesses/univer.md)
* **`#dom-first`** (1): [Moli](06_developer_tools_and_apps/moli.md)
* **`#dpo`** (2): [Dive into LLMs (动手学大模型)](01_llm_architecture_and_training/dive-into-llms.md), [MiniMind](01_llm_architecture_and_training/minimind.md)
* **`#drug-discovery`** (1): [Scientific Agent Skills (K-Dense AI](04_scientific_research_and_discovery/scientific-agent-skills.md)
* **`#e2b-compatible`** (1): [Dormice](02_agent_runtimes_and_harnesses/dormice.md)
* **`#edge-ai`** (1): [EnvoyMesh](02_agent_runtimes_and_harnesses/envoymesh.md)
* **`#edr-evasion`** (1): [Claude-Red](05_security_osint_and_guardrails/claude-red.md)
* **`#education`** (2): [LLMs from Scratch (Себастьян Рашка)](01_llm_architecture_and_training/LLMs-from-scratch.md), [OpenMAIC](02_agent_runtimes_and_harnesses/openmaic.md)
* **`#efficiency`** (1): [SoL-Pi](02_agent_runtimes_and_harnesses/sol-pi.md)
* **`#egress-control`** (1): [Pipelock](05_security_osint_and_guardrails/pipelock.md)
* **`#egress-proxy`** (1): [Smokescreen](05_security_osint_and_guardrails/smokescreen.md)
* **`#egui`** (1): [Fastpotify](06_developer_tools_and_apps/fastpotify.md)
* **`#email-recon`** (1): [User Scanner](05_security_osint_and_guardrails/user-scanner.md)
* **`#embeddings`** (1): [CLM](01_llm_architecture_and_training/clm.md)
* **`#engineering-ecosystem`** (1): [RuanYF Weekly](06_developer_tools_and_apps/ruanyf-weekly.md)
* **`#engineering-mentorship`** (1): [VibeWise](02_agent_runtimes_and_harnesses/vibe-wise.md)
* **`#enterprise-ai`** (3): [Claude Knowledge Work Plugins](02_agent_runtimes_and_harnesses/claude-knowledge-work-plugins.md), [Google AX](02_agent_runtimes_and_harnesses/google-ax.md), [Paperclip](02_agent_runtimes_and_harnesses/paperclip.md)
* **`#enterprise-data`** (1): [HydraDB](03_knowledge_graphs_and_ontologies/hydradb.md)
* **`#enterprise-guardrails`** (1): [Evenfire](02_agent_runtimes_and_harnesses/evenfire.md)
* **`#envoymesh`** (1): [EnvoyMesh](02_agent_runtimes_and_harnesses/envoymesh.md)
* **`#episodic-memory`** (1): [Hindsight](02_agent_runtimes_and_harnesses/hindsight.md)
* **`#evenfire`** (1): [Evenfire](02_agent_runtimes_and_harnesses/evenfire.md)
* **`#evidence-based`** (1): [Up (人生进阶指南)](00_strategy_and_roadmaps/up.md)
* **`#evidence-ledger`** (1): [PRAXIST](04_scientific_research_and_discovery/praxist.md)
* **`#evolutionary-search`** (1): [PRAXIST](04_scientific_research_and_discovery/praxist.md)
* **`#experience-replay`** (1): [Reef](02_agent_runtimes_and_harnesses/reef.md)
* **`#experiment-tracking`** (1): [alphaXiv OpenResearch](04_scientific_research_and_discovery/openresearch.md)
* **`#exploit-development`** (1): [Claude-Red](05_security_osint_and_guardrails/claude-red.md)
* **`#faang-interview`** (1): [System Design Notes](00_strategy_and_roadmaps/system-design-notes.md)
* **`#fail-closed`** (1): [TCB & Reference Monitor](05_security_osint_and_guardrails/tcb-agent-security.md)
* **`#fallback-routing`** (1): [Agent-Reach](02_agent_runtimes_and_harnesses/agent-reach.md)
* **`#fine-tuning`** (1): [LLM-Master](01_llm_architecture_and_training/llm-master.md)
* **`#formal-verification`** (1): [NVIDIA OpenShell](05_security_osint_and_guardrails/openshell.md)
* **`#formatting`** (1): [i-have-adhd](02_agent_runtimes_and_harnesses/i-have-adhd.md)
* **`#fq-book`** (1): [FQ-Book](05_security_osint_and_guardrails/fq-book.md)
* **`#from-scratch`** (1): [LLMs from Scratch (Себастьян Рашка)](01_llm_architecture_and_training/LLMs-from-scratch.md)
* **`#frontend`** (2): [Awesome DESIGN.md](02_agent_runtimes_and_harnesses/awesome-design-md.md), [Impeccable](02_agent_runtimes_and_harnesses/impeccable.md)
* **`#fuzzing`** (1): [HuntProxy](05_security_osint_and_guardrails/huntproxy.md)
* **`#gfw`** (1): [FQ-Book](05_security_osint_and_guardrails/fq-book.md)
* **`#ghost-security`** (1): [Ghost Security](05_security_osint_and_guardrails/ghost-security.md)
* **`#git-diff`** (1): [Open Code Review](02_agent_runtimes_and_harnesses/open-code-review.md)
* **`#git-integration`** (1): [AI-Memory](02_agent_runtimes_and_harnesses/ai-memory.md)
* **`#git-worktrees`** (1): [alphaXiv OpenResearch](04_scientific_research_and_discovery/openresearch.md)
* **`#github`** (1): [Agent-Reach](02_agent_runtimes_and_harnesses/agent-reach.md)
* **`#go`** (8): [Docker Agent](02_agent_runtimes_and_harnesses/docker-agent.md), [Google AX](02_agent_runtimes_and_harnesses/google-ax.md), [Magpie](02_agent_runtimes_and_harnesses/magpie.md), [Open Code Review](02_agent_runtimes_and_harnesses/open-code-review.md), [ARTEX](05_security_osint_and_guardrails/artex.md), [Ghost Security](05_security_osint_and_guardrails/ghost-security.md), [Pipelock](05_security_osint_and_guardrails/pipelock.md), [Smokescreen](05_security_osint_and_guardrails/smokescreen.md)
* **`#google-ax`** (2): [Docker Agent](02_agent_runtimes_and_harnesses/docker-agent.md), [Google AX](02_agent_runtimes_and_harnesses/google-ax.md)
* **`#gpui`** (1): [Disktree](06_developer_tools_and_apps/disktree.md)
* **`#graph-database`** (1): [HydraDB](03_knowledge_graphs_and_ontologies/hydradb.md)
* **`#grpo`** (2): [AI Engineering from Scratch (Рохит Гумаре](01_llm_architecture_and_training/ai-engineering-from-scratch.md), [Reasoning from Scratch (Себастьян Рашка](01_llm_architecture_and_training/reasoning-from-scratch.md)
* **`#guardrails`** (2): [CL4R1T4S](05_security_osint_and_guardrails/CL4R1T4S.md), [GPT-5.6 Instruct](05_security_osint_and_guardrails/gpt-5.6-instruct.md)
* **`#gvisor`** (1): [Dormice](02_agent_runtimes_and_harnesses/dormice.md)
* **`#hardware-constraints`** (1): [AI Infra Book](01_llm_architecture_and_training/ai-infra-book.md)
* **`#harness-engineering`** (2): [AI Agent Book](02_agent_runtimes_and_harnesses/ai-agent-book.md), [Learn Harness Engineering (Курс WalkingLabs](02_agent_runtimes_and_harnesses/learn-harness-engineering.md)
* **`#headless-browser`** (3): [HuntProxy](05_security_osint_and_guardrails/huntproxy.md), [Moli](06_developer_tools_and_apps/moli.md), [Obscura](06_developer_tools_and_apps/obscura.md)
* **`#high-availability`** (1): [System Design Notes](00_strategy_and_roadmaps/system-design-notes.md)
* **`#high-performance`** (3): [ZeroBoot](02_agent_runtimes_and_harnesses/zeroboot.md), [Disktree](06_developer_tools_and_apps/disktree.md), [RustFS](06_developer_tools_and_apps/rustfs.md)
* **`#hindsight`** (1): [Hindsight](02_agent_runtimes_and_harnesses/hindsight.md)
* **`#html`** (1): [Diagram Design](02_agent_runtimes_and_harnesses/diagram-design.md)
* **`#html-reporting`** (1): [Answer Me with HTML](02_agent_runtimes_and_harnesses/answer-me-with-html.md)
* **`#human-agent-society`** (1): [Reef](02_agent_runtimes_and_harnesses/reef.md)
* **`#human-in-the-loop`** (4): [OpenDots](02_agent_runtimes_and_harnesses/opendots.md), [VibeWise](02_agent_runtimes_and_harnesses/vibe-wise.md), [ARTEX](05_security_osint_and_guardrails/artex.md), [Tencent BrowserSkill](06_developer_tools_and_apps/browserskill.md)
* **`#huntproxy`** (1): [HuntProxy](05_security_osint_and_guardrails/huntproxy.md)
* **`#hybrid-search`** (1): [zvec-grep (zg)](02_agent_runtimes_and_harnesses/zvec-grep.md)
* **`#hydradb`** (1): [HydraDB](03_knowledge_graphs_and_ontologies/hydradb.md)
* **`#iceberg`** (1): [RustFS](06_developer_tools_and_apps/rustfs.md)
* **`#idle-zero-cost`** (1): [Dormice](02_agent_runtimes_and_harnesses/dormice.md)
* **`#impeccable`** (1): [Impeccable](02_agent_runtimes_and_harnesses/impeccable.md)
* **`#inference-optimization`** (2): [Laya](01_llm_architecture_and_training/laya.md), [OpenJev](01_llm_architecture_and_training/openjev.md)
* **`#inference-scaling`** (1): [Reasoning from Scratch (Себастьян Рашка](01_llm_architecture_and_training/reasoning-from-scratch.md)
* **`#infonce`** (1): [CLM](01_llm_architecture_and_training/clm.md)
* **`#intent-routing`** (1): [Magpie](02_agent_runtimes_and_harnesses/magpie.md)
* **`#interactive-learning`** (1): [OpenMAIC](02_agent_runtimes_and_harnesses/openmaic.md)
* **`#interview-prep`** (2): [AI Engineering Interviews](00_strategy_and_roadmaps/ai-engineering-interviews.md), [LLM-Master](01_llm_architecture_and_training/llm-master.md)
* **`#ipfs`** (1): [FQ-Book](05_security_osint_and_guardrails/fq-book.md)
* **`#isolation`** (1): [Coop](05_security_osint_and_guardrails/coop.md)
* **`#jadx`** (1): [APK-Reverse](05_security_osint_and_guardrails/apk-reverse.md)
* **`#jailbreak-analysis`** (1): [CL4R1T4S](05_security_osint_and_guardrails/CL4R1T4S.md)
* **`#jailbreak-testing`** (1): [GPT-5.6 Instruct](05_security_osint_and_guardrails/gpt-5.6-instruct.md)
* **`#jaredpalmer`** (1): [Kev](01_llm_architecture_and_training/kev.md)
* **`#jev-chat-jarvis`** (1): [Jev-Chat Jarvis](02_agent_runtimes_and_harnesses/jev-chat-jarvis.md)
* **`#jev-ecosystem`** (1): [Awesome-Jev](02_agent_runtimes_and_harnesses/awesome-jev.md)
* **`#jev-ultrafast`** (1): [Jev Ultrafast](02_agent_runtimes_and_harnesses/jev-ultrafast.md)
* **`#json-findings`** (1): [Cloudflare Security Audit Skill](05_security_osint_and_guardrails/security-audit-skill.md)
* **`#jupyter`** (1): [Dive into LLMs (动手学大模型)](01_llm_architecture_and_training/dive-into-llms.md)
* **`#kernel-hardening`** (1): [Анатомия ядра Linux и харденинг контейнеров](05_security_osint_and_guardrails/linux-kernel-and-container-hardening.md)
* **`#kernel-security`** (1): [NVIDIA OpenShell](05_security_osint_and_guardrails/openshell.md)
* **`#kev`** (1): [Kev](01_llm_architecture_and_training/kev.md)
* **`#knowledge-graphs`** (3): [HydraDB](03_knowledge_graphs_and_ontologies/hydradb.md), [Semantica AGI](03_knowledge_graphs_and_ontologies/semantica.md), [Utopia](03_knowledge_graphs_and_ontologies/utopia.md)
* **`#knowledge-vault`** (1): [Hyperresearch](04_scientific_research_and_discovery/hyperresearch.md)
* **`#knowledge-work`** (1): [Claude Knowledge Work Plugins](02_agent_runtimes_and_harnesses/claude-knowledge-work-plugins.md)
* **`#kotlin`** (1): [Jev-Chat Jarvis](02_agent_runtimes_and_harnesses/jev-chat-jarvis.md)
* **`#kubernetes`** (1): [NVIDIA OpenShell](05_security_osint_and_guardrails/openshell.md)
* **`#kubernetes-for-agents`** (1): [Google AX](02_agent_runtimes_and_harnesses/google-ax.md)
* **`#kv-cache`** (2): [AI Infra Book](01_llm_architecture_and_training/ai-infra-book.md), [AI Agent Book](02_agent_runtimes_and_harnesses/ai-agent-book.md)
* **`#latex`** (1): [Academic Research Skills](04_scientific_research_and_discovery/academic-research-skills.md)
* **`#laya`** (1): [Laya](01_llm_architecture_and_training/laya.md)
* **`#learning-roadmap`** (1): [Capstone Roadmap](00_strategy_and_roadmaps/capstone-engineering-roadmap.md)
* **`#lethal-trifecta`** (1): [Архитектура Tool Broker & Execution Blocker](02_agent_runtimes_and_harnesses/tool-broker-architecture.md)
* **`#librespot`** (1): [Fastpotify](06_developer_tools_and_apps/fastpotify.md)
* **`#lifelong-learning`** (1): [Up (人生进阶指南)](00_strategy_and_roadmaps/up.md)
* **`#lightweight-models`** (1): [MiniMind](01_llm_architecture_and_training/minimind.md)
* **`#line-level-precision`** (1): [Open Code Review](02_agent_runtimes_and_harnesses/open-code-review.md)
* **`#linting`** (1): [Impeccable](02_agent_runtimes_and_harnesses/impeccable.md)
* **`#linux-insides`** (1): [Анатомия ядра Linux и харденинг контейнеров](05_security_osint_and_guardrails/linux-kernel-and-container-hardening.md)
* **`#linux-kernel`** (1): [Анатомия ядра Linux и харденинг контейнеров](05_security_osint_and_guardrails/linux-kernel-and-container-hardening.md)
* **`#llm`** (3): [LLMs from Scratch (Себастьян Рашка)](01_llm_architecture_and_training/LLMs-from-scratch.md), [Dive into LLMs (动手学大模型)](01_llm_architecture_and_training/dive-into-llms.md), [MiniMind](01_llm_architecture_and_training/minimind.md)
* **`#llm-infra`** (1): [AI Engineering Interviews](00_strategy_and_roadmaps/ai-engineering-interviews.md)
* **`#llm-master`** (1): [LLM-Master](01_llm_architecture_and_training/llm-master.md)
* **`#llm-ready`** (1): [Crawl4AI](06_developer_tools_and_apps/crawl4ai.md)
* **`#llm-roadmap`** (1): [LLM-Master](01_llm_architecture_and_training/llm-master.md)
* **`#llm-security`** (1): [API Relay Audit](05_security_osint_and_guardrails/api-relay-audit.md)
* **`#local-first`** (2): [zvec-grep (zg)](02_agent_runtimes_and_harnesses/zvec-grep.md), [Utopia](03_knowledge_graphs_and_ontologies/utopia.md)
* **`#local-llm`** (1): [OpenJev](01_llm_architecture_and_training/openjev.md)
* **`#local-training`** (1): [Kev](01_llm_architecture_and_training/kev.md)
* **`#long-term-memory`** (1): [AI-Memory](02_agent_runtimes_and_harnesses/ai-memory.md)
* **`#loop-breaker`** (1): [Архитектура Tool Broker & Execution Blocker](02_agent_runtimes_and_harnesses/tool-broker-architecture.md)
* **`#lora`** (2): [Dive into LLMs (动手学大模型)](01_llm_architecture_and_training/dive-into-llms.md), [MiniMind](01_llm_architecture_and_training/minimind.md)
* **`#macbook`** (1): [Kev](01_llm_architecture_and_training/kev.md)
* **`#magpie`** (1): [Magpie](02_agent_runtimes_and_harnesses/magpie.md)
* **`#markdown`** (1): [Crawl4AI](06_developer_tools_and_apps/crawl4ai.md)
* **`#material-design`** (1): [M3E Canvas](02_agent_runtimes_and_harnesses/m3e-canvas.md)
* **`#mcp`** (16): [AI Engineering from Scratch (Рохит Гумаре](01_llm_architecture_and_training/ai-engineering-from-scratch.md), [LLM-Master](01_llm_architecture_and_training/llm-master.md), [Agent-Reach](02_agent_runtimes_and_harnesses/agent-reach.md), [Agent-Skills](02_agent_runtimes_and_harnesses/agent-skills.md), [AI Agent Book](02_agent_runtimes_and_harnesses/ai-agent-book.md), [Claude Knowledge Work Plugins](02_agent_runtimes_and_harnesses/claude-knowledge-work-plugins.md), [Docker Agent](02_agent_runtimes_and_harnesses/docker-agent.md), [Learn Harness Engineering (Курс WalkingLabs](02_agent_runtimes_and_harnesses/learn-harness-engineering.md), [Utopia](03_knowledge_graphs_and_ontologies/utopia.md), [Hyperresearch](04_scientific_research_and_discovery/hyperresearch.md), [ARTEX](05_security_osint_and_guardrails/artex.md), [Ghost Security](05_security_osint_and_guardrails/ghost-security.md), [HuntProxy](05_security_osint_and_guardrails/huntproxy.md), [SkillSpector](05_security_osint_and_guardrails/skillspector.md), [AIHawk](06_developer_tools_and_apps/ai-hawk.md), [cost-xray](06_developer_tools_and_apps/cost-xray.md)
* **`#mcp-router`** (1): [Архитектура Tool Broker & Execution Blocker](02_agent_runtimes_and_harnesses/tool-broker-architecture.md)
* **`#mcp-security`** (2): [AI/ML Pentesting Roadmap (2026 Edition)](05_security_osint_and_guardrails/ai-ml-pentest-roadmap.md), [Pipelock](05_security_osint_and_guardrails/pipelock.md)
* **`#mediator-receipts`** (1): [Pipelock](05_security_osint_and_guardrails/pipelock.md)
* **`#micro-runtime`** (1): [Monty](02_agent_runtimes_and_harnesses/monty.md)
* **`#micro-vm`** (2): [ArcBox](02_agent_runtimes_and_harnesses/arcbox.md), [ZeroBoot](02_agent_runtimes_and_harnesses/zeroboot.md)
* **`#microservices`** (1): [System Design 101](06_developer_tools_and_apps/system-design-101.md)
* **`#microvm`** (1): [Coop](05_security_osint_and_guardrails/coop.md)
* **`#minimal-code`** (1): [Ponytail](02_agent_runtimes_and_harnesses/ponytail.md)
* **`#minio-alternative`** (1): [RustFS](06_developer_tools_and_apps/rustfs.md)
* **`#mitm-proxy`** (1): [Ghost Security](05_security_osint_and_guardrails/ghost-security.md)
* **`#mitmproxy`** (1): [cost-xray](06_developer_tools_and_apps/cost-xray.md)
* **`#mlx`** (1): [Kev](01_llm_architecture_and_training/kev.md)
* **`#mobile-agent`** (1): [Jev-Chat Jarvis](02_agent_runtimes_and_harnesses/jev-chat-jarvis.md)
* **`#model-routing`** (1): [Magpie](02_agent_runtimes_and_harnesses/magpie.md)
* **`#model-substitution`** (1): [API Relay Audit](05_security_osint_and_guardrails/api-relay-audit.md)
* **`#moli`** (1): [Moli](06_developer_tools_and_apps/moli.md)
* **`#multi-agent`** (3): [AI Agent Book](02_agent_runtimes_and_harnesses/ai-agent-book.md), [OpenMAIC](02_agent_runtimes_and_harnesses/openmaic.md), [Paperclip](02_agent_runtimes_and_harnesses/paperclip.md)
* **`#multi-platform`** (1): [Agent-Reach](02_agent_runtimes_and_harnesses/agent-reach.md)
* **`#multilingual-ai`** (1): [Laya](01_llm_architecture_and_training/laya.md)
* **`#namespaces`** (1): [Анатомия ядра Linux и харденинг контейнеров](05_security_osint_and_guardrails/linux-kernel-and-container-hardening.md)
* **`#ncc-group`** (1): [Анатомия ядра Linux и харденинг контейнеров](05_security_osint_and_guardrails/linux-kernel-and-container-hardening.md)
* **`#network-security`** (2): [FQ-Book](05_security_osint_and_guardrails/fq-book.md), [Smokescreen](05_security_osint_and_guardrails/smokescreen.md)
* **`#nextjs`** (1): [ARTEX](05_security_osint_and_guardrails/artex.md)
* **`#no-mermaid`** (1): [Diagram Design](02_agent_runtimes_and_harnesses/diagram-design.md)
* **`#non-autoregressive`** (2): [Laya](01_llm_architecture_and_training/laya.md), [Awesome-Jev](02_agent_runtimes_and_harnesses/awesome-jev.md)
* **`#non-invasive`** (1): [Jev-Chat Jarvis](02_agent_runtimes_and_harnesses/jev-chat-jarvis.md)
* **`#nvidia`** (3): [SoL-Pi](02_agent_runtimes_and_harnesses/sol-pi.md), [NVIDIA OpenShell](05_security_osint_and_guardrails/openshell.md), [SkillSpector](05_security_osint_and_guardrails/skillspector.md)
* **`#object-storage`** (2): [HydraDB](03_knowledge_graphs_and_ontologies/hydradb.md), [RustFS](06_developer_tools_and_apps/rustfs.md)
* **`#observation-pack`** (1): [SoL-Pi](02_agent_runtimes_and_harnesses/sol-pi.md)
* **`#oci`** (1): [ArcBox](02_agent_runtimes_and_harnesses/arcbox.md)
* **`#oci-runtime`** (1): [Docker Agent](02_agent_runtimes_and_harnesses/docker-agent.md)
* **`#offensive-ai`** (1): [AI/ML Pentesting Roadmap (2026 Edition)](05_security_osint_and_guardrails/ai-ml-pentest-roadmap.md)
* **`#offensive-security`** (2): [ARTEX](05_security_osint_and_guardrails/artex.md), [Claude-Red](05_security_osint_and_guardrails/claude-red.md)
* **`#office-harness`** (1): [Univer](02_agent_runtimes_and_harnesses/univer.md)
* **`#ontologies`** (1): [Utopia](03_knowledge_graphs_and_ontologies/utopia.md)
* **`#open-code-review`** (1): [Open Code Review](02_agent_runtimes_and_harnesses/open-code-review.md)
* **`#open-source-book`** (2): [AI Infra Book](01_llm_architecture_and_training/ai-infra-book.md), [AI Agent Book](02_agent_runtimes_and_harnesses/ai-agent-book.md)
* **`#open-source-curation`** (1): [RuanYF Weekly](06_developer_tools_and_apps/ruanyf-weekly.md)
* **`#openbot`** (1): [OpenDots](02_agent_runtimes_and_harnesses/opendots.md)
* **`#opencode`** (1): [Magpie](02_agent_runtimes_and_harnesses/magpie.md)
* **`#opencypher`** (1): [HydraDB](03_knowledge_graphs_and_ontologies/hydradb.md)
* **`#opendots`** (1): [OpenDots](02_agent_runtimes_and_harnesses/opendots.md)
* **`#openjev`** (1): [OpenJev](01_llm_architecture_and_training/openjev.md)
* **`#openresearch`** (1): [alphaXiv OpenResearch](04_scientific_research_and_discovery/openresearch.md)
* **`#openshell`** (1): [NVIDIA OpenShell](05_security_osint_and_guardrails/openshell.md)
* **`#openspec`** (1): [OpenSpec](02_agent_runtimes_and_harnesses/openspec.md)
* **`#option-attention`** (6): [Kev](01_llm_architecture_and_training/kev.md), [Laya](01_llm_architecture_and_training/laya.md), [OpenJev](01_llm_architecture_and_training/openjev.md), [Awesome-Jev](02_agent_runtimes_and_harnesses/awesome-jev.md), [Jev-Chat Jarvis](02_agent_runtimes_and_harnesses/jev-chat-jarvis.md), [Jev Ultrafast](02_agent_runtimes_and_harnesses/jev-ultrafast.md)
* **`#orx-cli`** (1): [alphaXiv OpenResearch](04_scientific_research_and_discovery/openresearch.md)
* **`#osint`** (1): [User Scanner](05_security_osint_and_guardrails/user-scanner.md)
* **`#owasp-agentic`** (1): [AI/ML Pentesting Roadmap (2026 Edition)](05_security_osint_and_guardrails/ai-ml-pentest-roadmap.md)
* **`#owasp-llm`** (1): [AI/ML Pentesting Roadmap (2026 Edition)](05_security_osint_and_guardrails/ai-ml-pentest-roadmap.md)
* **`#p2p-mesh`** (1): [EnvoyMesh](02_agent_runtimes_and_harnesses/envoymesh.md)
* **`#paperclip`** (1): [Paperclip](02_agent_runtimes_and_harnesses/paperclip.md)
* **`#paul-bakaus`** (1): [Impeccable](02_agent_runtimes_and_harnesses/impeccable.md)
* **`#pdf`** (1): [Univer](02_agent_runtimes_and_harnesses/univer.md)
* **`#peer-review`** (2): [Academic Research Skills](04_scientific_research_and_discovery/academic-research-skills.md), [Hyperresearch](04_scientific_research_and_discovery/hyperresearch.md)
* **`#peer-to-peer`** (1): [EnvoyMesh](02_agent_runtimes_and_harnesses/envoymesh.md)
* **`#pen-testing`** (1): [Claude-Red](05_security_osint_and_guardrails/claude-red.md)
* **`#permissions`** (1): [Docker Agent](02_agent_runtimes_and_harnesses/docker-agent.md)
* **`#personal-growth`** (1): [Up (人生进阶指南)](00_strategy_and_roadmaps/up.md)
* **`#pi-agent`** (1): [SoL-Pi](02_agent_runtimes_and_harnesses/sol-pi.md)
* **`#planning`** (1): [OpenSpec](02_agent_runtimes_and_harnesses/openspec.md)
* **`#playwright`** (3): [AIHawk](06_developer_tools_and_apps/ai-hawk.md), [Crawl4AI](06_developer_tools_and_apps/crawl4ai.md), [Moli](06_developer_tools_and_apps/moli.md)
* **`#ponytail`** (1): [Ponytail](02_agent_runtimes_and_harnesses/ponytail.md)
* **`#post-training`** (1): [AI Agent Book](02_agent_runtimes_and_harnesses/ai-agent-book.md)
* **`#pretraining`** (2): [Dive into LLMs (动手学大模型)](01_llm_architecture_and_training/dive-into-llms.md), [MiniMind](01_llm_architecture_and_training/minimind.md)
* **`#problem-solving`** (1): [Up (人生进阶指南)](00_strategy_and_roadmaps/up.md)
* **`#productivity`** (2): [Claude Knowledge Work Plugins](02_agent_runtimes_and_harnesses/claude-knowledge-work-plugins.md), [i-have-adhd](02_agent_runtimes_and_harnesses/i-have-adhd.md)
* **`#programmatic-tool-calling`** (1): [Monty](02_agent_runtimes_and_harnesses/monty.md)
* **`#prompt-cache`** (1): [Magpie](02_agent_runtimes_and_harnesses/magpie.md)
* **`#prompt-engineering`** (9): [LLM-Master](01_llm_architecture_and_training/llm-master.md), [Answer Me with HTML](02_agent_runtimes_and_harnesses/answer-me-with-html.md), [Awesome DESIGN.md](02_agent_runtimes_and_harnesses/awesome-design-md.md), [i-have-adhd](02_agent_runtimes_and_harnesses/i-have-adhd.md), [M3E Canvas](02_agent_runtimes_and_harnesses/m3e-canvas.md), [Ponytail](02_agent_runtimes_and_harnesses/ponytail.md), [CL4R1T4S](05_security_osint_and_guardrails/CL4R1T4S.md), [Claude-Red](05_security_osint_and_guardrails/claude-red.md), [cost-xray](06_developer_tools_and_apps/cost-xray.md)
* **`#prompt-injection`** (6): [AI/ML Pentesting Roadmap (2026 Edition)](05_security_osint_and_guardrails/ai-ml-pentest-roadmap.md), [API Relay Audit](05_security_osint_and_guardrails/api-relay-audit.md), [Pipelock](05_security_osint_and_guardrails/pipelock.md), [Cloudflare Security Audit Skill](05_security_osint_and_guardrails/security-audit-skill.md), [SkillSpector](05_security_osint_and_guardrails/skillspector.md), [TCB & Reference Monitor](05_security_osint_and_guardrails/tcb-agent-security.md)
* **`#prototyping`** (1): [M3E Canvas](02_agent_runtimes_and_harnesses/m3e-canvas.md)
* **`#prov-o`** (1): [Semantica AGI](03_knowledge_graphs_and_ontologies/semantica.md)
* **`#proxy`** (1): [FQ-Book](05_security_osint_and_guardrails/fq-book.md)
* **`#pubmed`** (1): [Scientific Agent Skills (K-Dense AI](04_scientific_research_and_discovery/scientific-agent-skills.md)
* **`#pull-requests`** (1): [Whiteboard](06_developer_tools_and_apps/whiteboard.md)
* **`#pydantic`** (1): [Monty](02_agent_runtimes_and_harnesses/monty.md)
* **`#python`** (12): [CLM](01_llm_architecture_and_training/clm.md), [Kev](01_llm_architecture_and_training/kev.md), [Laya](01_llm_architecture_and_training/laya.md), [OpenJev](01_llm_architecture_and_training/openjev.md), [AutoHarness](02_agent_runtimes_and_harnesses/autoharness.md), [Hindsight](02_agent_runtimes_and_harnesses/hindsight.md), [Jev Ultrafast](02_agent_runtimes_and_harnesses/jev-ultrafast.md), [Reef](02_agent_runtimes_and_harnesses/reef.md), [VibeWise](02_agent_runtimes_and_harnesses/vibe-wise.md), [APK-Reverse](05_security_osint_and_guardrails/apk-reverse.md), [User Scanner](05_security_osint_and_guardrails/user-scanner.md), [AIHawk](06_developer_tools_and_apps/ai-hawk.md)
* **`#python-interpreter`** (1): [Monty](02_agent_runtimes_and_harnesses/monty.md)
* **`#pytorch`** (5): [LLMs from Scratch (Себастьян Рашка)](01_llm_architecture_and_training/LLMs-from-scratch.md), [CLM](01_llm_architecture_and_training/clm.md), [Kev](01_llm_architecture_and_training/kev.md), [MiniMind](01_llm_architecture_and_training/minimind.md), [OpenJev](01_llm_architecture_and_training/openjev.md)
* **`#quantization`** (1): [Dive into LLMs (动手学大模型)](01_llm_architecture_and_training/dive-into-llms.md)
* **`#quota-failover`** (1): [Magpie](02_agent_runtimes_and_harnesses/magpie.md)
* **`#qwen`** (2): [Kev](01_llm_architecture_and_training/kev.md), [OpenJev](01_llm_architecture_and_training/openjev.md)
* **`#r-and-d`** (1): [PRAXIST](04_scientific_research_and_discovery/praxist.md)
* **`#rag`** (5): [AI Engineering Interviews](00_strategy_and_roadmaps/ai-engineering-interviews.md), [AI Engineering from Scratch (Рохит Гумаре](01_llm_architecture_and_training/ai-engineering-from-scratch.md), [CLM](01_llm_architecture_and_training/clm.md), [LLM-Master](01_llm_architecture_and_training/llm-master.md), [Crawl4AI](06_developer_tools_and_apps/crawl4ai.md)
* **`#rag-poisoning`** (1): [AI/ML Pentesting Roadmap (2026 Edition)](05_security_osint_and_guardrails/ai-ml-pentest-roadmap.md)
* **`#rbac`** (1): [Evenfire](02_agent_runtimes_and_harnesses/evenfire.md)
* **`#rdma`** (1): [AI Infra Book](01_llm_architecture_and_training/ai-infra-book.md)
* **`#react`** (2): [M3E Canvas](02_agent_runtimes_and_harnesses/m3e-canvas.md), [Paperclip](02_agent_runtimes_and_harnesses/paperclip.md)
* **`#reaper`** (1): [Ghost Security](05_security_osint_and_guardrails/ghost-security.md)
* **`#reasoning`** (1): [Reasoning from Scratch (Себастьян Рашка](01_llm_architecture_and_training/reasoning-from-scratch.md)
* **`#red-teaming`** (4): [CL4R1T4S](05_security_osint_and_guardrails/CL4R1T4S.md), [AI/ML Pentesting Roadmap (2026 Edition)](05_security_osint_and_guardrails/ai-ml-pentest-roadmap.md), [Claude-Red](05_security_osint_and_guardrails/claude-red.md), [GPT-5.6 Instruct](05_security_osint_and_guardrails/gpt-5.6-instruct.md)
* **`#reddit`** (1): [Agent-Reach](02_agent_runtimes_and_harnesses/agent-reach.md)
* **`#reef`** (1): [Reef](02_agent_runtimes_and_harnesses/reef.md)
* **`#reference-monitor`** (2): [NVIDIA OpenShell](05_security_osint_and_guardrails/openshell.md), [TCB & Reference Monitor](05_security_osint_and_guardrails/tcb-agent-security.md)
* **`#reinforcement-learning`** (1): [Reasoning from Scratch (Себастьян Рашка](01_llm_architecture_and_training/reasoning-from-scratch.md)
* **`#representation-learning`** (1): [CLM](01_llm_architecture_and_training/clm.md)
* **`#reproducible-research`** (1): [alphaXiv OpenResearch](04_scientific_research_and_discovery/openresearch.md)
* **`#research-agents`** (1): [alphaXiv OpenResearch](04_scientific_research_and_discovery/openresearch.md)
* **`#rete`** (1): [Semantica AGI](03_knowledge_graphs_and_ontologies/semantica.md)
* **`#reverse-engineering`** (1): [APK-Reverse](05_security_osint_and_guardrails/apk-reverse.md)
* **`#rlcd`** (1): [Laya](01_llm_architecture_and_training/laya.md)
* **`#rlhf`** (1): [Dive into LLMs (动手学大模型)](01_llm_architecture_and_training/dive-into-llms.md)
* **`#rlvr`** (1): [Reasoning from Scratch (Себастьян Рашка](01_llm_architecture_and_training/reasoning-from-scratch.md)
* **`#roadmap`** (1): [AI Engineering from Scratch (Рохит Гумаре](01_llm_architecture_and_training/ai-engineering-from-scratch.md)
* **`#roofline-model`** (1): [AI Infra Book](01_llm_architecture_and_training/ai-infra-book.md)
* **`#ruanyf-weekly`** (1): [RuanYF Weekly](06_developer_tools_and_apps/ruanyf-weekly.md)
* **`#rust`** (17): [AI-Memory](02_agent_runtimes_and_harnesses/ai-memory.md), [ArcBox](02_agent_runtimes_and_harnesses/arcbox.md), [Atlas](02_agent_runtimes_and_harnesses/atlas.md), [Monty](02_agent_runtimes_and_harnesses/monty.md), [ZeroBoot](02_agent_runtimes_and_harnesses/zeroboot.md), [HydraDB](03_knowledge_graphs_and_ontologies/hydradb.md), [Utopia](03_knowledge_graphs_and_ontologies/utopia.md), [alphaXiv OpenResearch](04_scientific_research_and_discovery/openresearch.md), [Coop](05_security_osint_and_guardrails/coop.md), [HuntProxy](05_security_osint_and_guardrails/huntproxy.md), [NVIDIA OpenShell](05_security_osint_and_guardrails/openshell.md), [Tencent BrowserSkill](06_developer_tools_and_apps/browserskill.md), [Disktree](06_developer_tools_and_apps/disktree.md), [Fastpotify](06_developer_tools_and_apps/fastpotify.md), [Moli](06_developer_tools_and_apps/moli.md), [Obscura](06_developer_tools_and_apps/obscura.md), [RustFS](06_developer_tools_and_apps/rustfs.md)
* **`#rustfs`** (1): [RustFS](06_developer_tools_and_apps/rustfs.md)
* **`#s3-compatible`** (1): [RustFS](06_developer_tools_and_apps/rustfs.md)
* **`#s3-storage`** (1): [HydraDB](03_knowledge_graphs_and_ontologies/hydradb.md)
* **`#sandboxing`** (7): [ArcBox](02_agent_runtimes_and_harnesses/arcbox.md), [Docker Agent](02_agent_runtimes_and_harnesses/docker-agent.md), [Google AX](02_agent_runtimes_and_harnesses/google-ax.md), [Анатомия ядра Linux и харденинг контейнеров](05_security_osint_and_guardrails/linux-kernel-and-container-hardening.md), [NVIDIA OpenShell](05_security_osint_and_guardrails/openshell.md), [Cloudflare Security Audit Skill](05_security_osint_and_guardrails/security-audit-skill.md), [TCB & Reference Monitor](05_security_osint_and_guardrails/tcb-agent-security.md)
* **`#sarif`** (1): [Cloudflare Security Audit Skill](05_security_osint_and_guardrails/security-audit-skill.md)
* **`#sast`** (1): [Ghost Security](05_security_osint_and_guardrails/ghost-security.md)
* **`#sca`** (1): [Ghost Security](05_security_osint_and_guardrails/ghost-security.md)
* **`#scalability`** (1): [System Design Notes](00_strategy_and_roadmaps/system-design-notes.md)
* **`#scientific-writing`** (1): [Academic Research Skills](04_scientific_research_and_discovery/academic-research-skills.md)
* **`#scopesentry`** (1): [ARTEX](05_security_osint_and_guardrails/artex.md)
* **`#sdd`** (1): [OpenSpec](02_agent_runtimes_and_harnesses/openspec.md)
* **`#search`** (1): [zvec-grep (zg)](02_agent_runtimes_and_harnesses/zvec-grep.md)
* **`#seccomp-bpf`** (1): [Анатомия ядра Linux и харденинг контейнеров](05_security_osint_and_guardrails/linux-kernel-and-container-hardening.md)
* **`#secret-broker`** (1): [TCB & Reference Monitor](05_security_osint_and_guardrails/tcb-agent-security.md)
* **`#secret-scanner`** (1): [APK-Reverse](05_security_osint_and_guardrails/apk-reverse.md)
* **`#security`** (5): [Monty](02_agent_runtimes_and_harnesses/monty.md), [Архитектура Tool Broker & Execution Blocker](02_agent_runtimes_and_harnesses/tool-broker-architecture.md), [Coop](05_security_osint_and_guardrails/coop.md), [GPT-5.6 Instruct](05_security_osint_and_guardrails/gpt-5.6-instruct.md), [User Scanner](05_security_osint_and_guardrails/user-scanner.md)
* **`#security-audit`** (2): [Ghost Security](05_security_osint_and_guardrails/ghost-security.md), [Cloudflare Security Audit Skill](05_security_osint_and_guardrails/security-audit-skill.md)
* **`#security-audit-skill`** (1): [Cloudflare Security Audit Skill](05_security_osint_and_guardrails/security-audit-skill.md)
* **`#security-guardrails`** (2): [ARTEX](05_security_osint_and_guardrails/artex.md), [NVIDIA OpenShell](05_security_osint_and_guardrails/openshell.md)
* **`#security-rules`** (1): [Open Code Review](02_agent_runtimes_and_harnesses/open-code-review.md)
* **`#security-workbench`** (1): [HuntProxy](05_security_osint_and_guardrails/huntproxy.md)
* **`#self-hosted`** (3): [Dormice](02_agent_runtimes_and_harnesses/dormice.md), [Evenfire](02_agent_runtimes_and_harnesses/evenfire.md), [Paperclip](02_agent_runtimes_and_harnesses/paperclip.md)
* **`#self-improving`** (1): [AutoHarness](02_agent_runtimes_and_harnesses/autoharness.md)
* **`#self-sovereign-identity`** (1): [EnvoyMesh](02_agent_runtimes_and_harnesses/envoymesh.md)
* **`#selinux`** (1): [Анатомия ядра Linux и харденинг контейнеров](05_security_osint_and_guardrails/linux-kernel-and-container-hardening.md)
* **`#semantic-search`** (2): [CLM](01_llm_architecture_and_training/clm.md), [zvec-grep (zg)](02_agent_runtimes_and_harnesses/zvec-grep.md)
* **`#senior-dev`** (1): [Ponytail](02_agent_runtimes_and_harnesses/ponytail.md)
* **`#sft`** (2): [Dive into LLMs (动手学大模型)](01_llm_architecture_and_training/dive-into-llms.md), [MiniMind](01_llm_architecture_and_training/minimind.md)
* **`#shacl`** (1): [Semantica AGI](03_knowledge_graphs_and_ontologies/semantica.md)
* **`#shadowsocks`** (1): [FQ-Book](05_security_osint_and_guardrails/fq-book.md)
* **`#sitemap-discovery`** (1): [HuntProxy](05_security_osint_and_guardrails/huntproxy.md)
* **`#skill-learning`** (1): [AutoHarness](02_agent_runtimes_and_harnesses/autoharness.md)
* **`#skill-md`** (1): [Claude-Red](05_security_osint_and_guardrails/claude-red.md)
* **`#skill-registry`** (1): [Agent-Skills](02_agent_runtimes_and_harnesses/agent-skills.md)
* **`#skill-scanner`** (1): [SkillSpector](05_security_osint_and_guardrails/skillspector.md)
* **`#slack`** (1): [OpenDots](02_agent_runtimes_and_harnesses/opendots.md)
* **`#slides`** (1): [Univer](02_agent_runtimes_and_harnesses/univer.md)
* **`#smali`** (1): [APK-Reverse](05_security_osint_and_guardrails/apk-reverse.md)
* **`#snyk-agent-scan`** (1): [Agent-Skills](02_agent_runtimes_and_harnesses/agent-skills.md)
* **`#socratic-planning`** (1): [Academic Research Skills](04_scientific_research_and_discovery/academic-research-skills.md)
* **`#software-design`** (1): [VibeWise](02_agent_runtimes_and_harnesses/vibe-wise.md)
* **`#source-control`** (1): [Atlas](02_agent_runtimes_and_harnesses/atlas.md)
* **`#spec-driven`** (1): [Agent-Skills](02_agent_runtimes_and_harnesses/agent-skills.md)
* **`#spec-driven-development`** (1): [OpenSpec](02_agent_runtimes_and_harnesses/openspec.md)
* **`#specs`** (1): [OpenSpec](02_agent_runtimes_and_harnesses/openspec.md)
* **`#spotify`** (1): [Fastpotify](06_developer_tools_and_apps/fastpotify.md)
* **`#spreadsheets`** (1): [Univer](02_agent_runtimes_and_harnesses/univer.md)
* **`#sse-anomalies`** (1): [API Relay Audit](05_security_osint_and_guardrails/api-relay-audit.md)
* **`#ssi`** (1): [EnvoyMesh](02_agent_runtimes_and_harnesses/envoymesh.md)
* **`#ssrf-prevention`** (3): [Pipelock](05_security_osint_and_guardrails/pipelock.md), [Smokescreen](05_security_osint_and_guardrails/smokescreen.md), [TCB & Reference Monitor](05_security_osint_and_guardrails/tcb-agent-security.md)
* **`#static-analysis`** (2): [APK-Reverse](05_security_osint_and_guardrails/apk-reverse.md), [SkillSpector](05_security_osint_and_guardrails/skillspector.md)
* **`#stealth-browser`** (1): [AIHawk](06_developer_tools_and_apps/ai-hawk.md)
* **`#storage-engine`** (1): [RustFS](06_developer_tools_and_apps/rustfs.md)
* **`#strategy`** (1): [Capstone Roadmap](00_strategy_and_roadmaps/capstone-engineering-roadmap.md)
* **`#stripe`** (1): [Smokescreen](05_security_osint_and_guardrails/smokescreen.md)
* **`#structured-extraction`** (1): [Crawl4AI](06_developer_tools_and_apps/crawl4ai.md)
* **`#supply-chain`** (1): [SkillSpector](05_security_osint_and_guardrails/skillspector.md)
* **`#supply-chain-security`** (1): [Agent-Skills](02_agent_runtimes_and_harnesses/agent-skills.md)
* **`#svg`** (1): [Diagram Design](02_agent_runtimes_and_harnesses/diagram-design.md)
* **`#system-1`** (3): [Awesome-Jev](02_agent_runtimes_and_harnesses/awesome-jev.md), [Jev-Chat Jarvis](02_agent_runtimes_and_harnesses/jev-chat-jarvis.md), [Jev Ultrafast](02_agent_runtimes_and_harnesses/jev-ultrafast.md)
* **`#system-1-models`** (3): [Kev](01_llm_architecture_and_training/kev.md), [Laya](01_llm_architecture_and_training/laya.md), [OpenJev](01_llm_architecture_and_training/openjev.md)
* **`#system-architecture`** (1): [Capstone Roadmap](00_strategy_and_roadmaps/capstone-engineering-roadmap.md)
* **`#system-design`** (5): [AI Engineering Interviews](00_strategy_and_roadmaps/ai-engineering-interviews.md), [System Design Notes](00_strategy_and_roadmaps/system-design-notes.md), [AI Infra Book](01_llm_architecture_and_training/ai-infra-book.md), [LLM-Master](01_llm_architecture_and_training/llm-master.md), [System Design 101](06_developer_tools_and_apps/system-design-101.md)
* **`#system-prompts`** (1): [CL4R1T4S](05_security_osint_and_guardrails/CL4R1T4S.md)
* **`#system-tools`** (1): [Disktree](06_developer_tools_and_apps/disktree.md)
* **`#systems-thinking`** (1): [Up (人生进阶指南)](00_strategy_and_roadmaps/up.md)
* **`#tab-borrowing`** (1): [Tencent BrowserSkill](06_developer_tools_and_apps/browserskill.md)
* **`#tcb`** (4): [Docker Agent](02_agent_runtimes_and_harnesses/docker-agent.md), [Pipelock](05_security_osint_and_guardrails/pipelock.md), [Smokescreen](05_security_osint_and_guardrails/smokescreen.md), [TCB & Reference Monitor](05_security_osint_and_guardrails/tcb-agent-security.md)
* **`#tcp-rst`** (1): [FQ-Book](05_security_osint_and_guardrails/fq-book.md)
* **`#tech-digest`** (1): [RuanYF Weekly](06_developer_tools_and_apps/ruanyf-weekly.md)
* **`#tencent`** (1): [Tencent BrowserSkill](06_developer_tools_and_apps/browserskill.md)
* **`#threat-modeling`** (1): [Docker Agent](02_agent_runtimes_and_harnesses/docker-agent.md)
* **`#tobi-lutke`** (1): [Disktree](06_developer_tools_and_apps/disktree.md)
* **`#token-diet`** (1): [SoL-Pi](02_agent_runtimes_and_harnesses/sol-pi.md)
* **`#token-efficiency`** (1): [Open Code Review](02_agent_runtimes_and_harnesses/open-code-review.md)
* **`#token-inspector`** (1): [cost-xray](06_developer_tools_and_apps/cost-xray.md)
* **`#token-optimization`** (1): [Answer Me with HTML](02_agent_runtimes_and_harnesses/answer-me-with-html.md)
* **`#tool-broker`** (1): [Архитектура Tool Broker & Execution Blocker](02_agent_runtimes_and_harnesses/tool-broker-architecture.md)
* **`#tool-call-tampering`** (1): [API Relay Audit](05_security_osint_and_guardrails/api-relay-audit.md)
* **`#tool-gateway`** (1): [Архитектура Tool Broker & Execution Blocker](02_agent_runtimes_and_harnesses/tool-broker-architecture.md)
* **`#tool-rag`** (1): [Архитектура Tool Broker & Execution Blocker](02_agent_runtimes_and_harnesses/tool-broker-architecture.md)
* **`#traffic-evidence`** (1): [ARTEX](05_security_osint_and_guardrails/artex.md)
* **`#trailofbits`** (1): [Coop](05_security_osint_and_guardrails/coop.md)
* **`#trajectory-logging`** (1): [Reef](02_agent_runtimes_and_harnesses/reef.md)
* **`#transformers`** (3): [LLMs from Scratch (Себастьян Рашка)](01_llm_architecture_and_training/LLMs-from-scratch.md), [Dive into LLMs (动手学大模型)](01_llm_architecture_and_training/dive-into-llms.md), [LLM-Master](01_llm_architecture_and_training/llm-master.md)
* **`#transparency`** (1): [CL4R1T4S](05_security_osint_and_guardrails/CL4R1T4S.md)
* **`#tree-sitter`** (1): [Atlas](02_agent_runtimes_and_harnesses/atlas.md)
* **`#treemap`** (1): [Disktree](06_developer_tools_and_apps/disktree.md)
* **`#trusted-computing-base`** (1): [TCB & Reference Monitor](05_security_osint_and_guardrails/tcb-agent-security.md)
* **`#twitter`** (1): [Agent-Reach](02_agent_runtimes_and_harnesses/agent-reach.md)
* **`#typed-decisions`** (1): [Laya](01_llm_architecture_and_training/laya.md)
* **`#typescript`** (11): [Agent-Skills](02_agent_runtimes_and_harnesses/agent-skills.md), [Dormice](02_agent_runtimes_and_harnesses/dormice.md), [EnvoyMesh](02_agent_runtimes_and_harnesses/envoymesh.md), [Evenfire](02_agent_runtimes_and_harnesses/evenfire.md), [Magpie](02_agent_runtimes_and_harnesses/magpie.md), [OpenDots](02_agent_runtimes_and_harnesses/opendots.md), [OpenMAIC](02_agent_runtimes_and_harnesses/openmaic.md), [OpenSpec](02_agent_runtimes_and_harnesses/openspec.md), [Paperclip](02_agent_runtimes_and_harnesses/paperclip.md), [Univer](02_agent_runtimes_and_harnesses/univer.md), [Whiteboard](06_developer_tools_and_apps/whiteboard.md)
* **`#ui-components`** (1): [Univer](02_agent_runtimes_and_harnesses/univer.md)
* **`#ui-ux`** (3): [Awesome DESIGN.md](02_agent_runtimes_and_harnesses/awesome-design-md.md), [Impeccable](02_agent_runtimes_and_harnesses/impeccable.md), [M3E Canvas](02_agent_runtimes_and_harnesses/m3e-canvas.md)
* **`#ultrafast`** (1): [Jev Ultrafast](02_agent_runtimes_and_harnesses/jev-ultrafast.md)
* **`#univer`** (1): [Univer](02_agent_runtimes_and_harnesses/univer.md)
* **`#up`** (1): [Up (人生进阶指南)](00_strategy_and_roadmaps/up.md)
* **`#username-scanner`** (1): [User Scanner](05_security_osint_and_guardrails/user-scanner.md)
* **`#ux`** (1): [i-have-adhd](02_agent_runtimes_and_harnesses/i-have-adhd.md)
* **`#v2ray`** (1): [FQ-Book](05_security_osint_and_guardrails/fq-book.md)
* **`#vcs`** (1): [Atlas](02_agent_runtimes_and_harnesses/atlas.md)
* **`#vector-search`** (2): [Hindsight](02_agent_runtimes_and_harnesses/hindsight.md), [zvec-grep (zg)](02_agent_runtimes_and_harnesses/zvec-grep.md)
* **`#verified-skills`** (1): [Agent-Skills](02_agent_runtimes_and_harnesses/agent-skills.md)
* **`#vibe-coding`** (3): [Impeccable](02_agent_runtimes_and_harnesses/impeccable.md), [M3E Canvas](02_agent_runtimes_and_harnesses/m3e-canvas.md), [VibeWise](02_agent_runtimes_and_harnesses/vibe-wise.md)
* **`#vibe-wise`** (1): [VibeWise](02_agent_runtimes_and_harnesses/vibe-wise.md)
* **`#virtualization`** (1): [ZeroBoot](02_agent_runtimes_and_harnesses/zeroboot.md)
* **`#visual-architecture`** (1): [Whiteboard](06_developer_tools_and_apps/whiteboard.md)
* **`#visual-guide`** (1): [System Design 101](06_developer_tools_and_apps/system-design-101.md)
* **`#vllm`** (5): [AI Engineering Interviews](00_strategy_and_roadmaps/ai-engineering-interviews.md), [AI Engineering from Scratch (Рохит Гумаре](01_llm_architecture_and_training/ai-engineering-from-scratch.md), [AI Infra Book](01_llm_architecture_and_training/ai-infra-book.md), [Dive into LLMs (动手学大模型)](01_llm_architecture_and_training/dive-into-llms.md), [LLM-Master](01_llm_architecture_and_training/llm-master.md)
* **`#vpn`** (1): [FQ-Book](05_security_osint_and_guardrails/fq-book.md)
* **`#vulnerability-assessment`** (1): [Cloudflare Security Audit Skill](05_security_osint_and_guardrails/security-audit-skill.md)
* **`#vulnerability-research`** (1): [Claude-Red](05_security_osint_and_guardrails/claude-red.md)
* **`#web-automation`** (2): [Jev Ultrafast](02_agent_runtimes_and_harnesses/jev-ultrafast.md), [AIHawk](06_developer_tools_and_apps/ai-hawk.md)
* **`#web-crawler`** (1): [Crawl4AI](06_developer_tools_and_apps/crawl4ai.md)
* **`#web-scraping`** (5): [Agent-Reach](02_agent_runtimes_and_harnesses/agent-reach.md), [Hyperresearch](04_scientific_research_and_discovery/hyperresearch.md), [Crawl4AI](06_developer_tools_and_apps/crawl4ai.md), [Moli](06_developer_tools_and_apps/moli.md), [Obscura](06_developer_tools_and_apps/obscura.md)
* **`#web-security`** (1): [HuntProxy](05_security_osint_and_guardrails/huntproxy.md)
* **`#webdriver-bidi`** (1): [Moli](06_developer_tools_and_apps/moli.md)
* **`#webrtc`** (1): [OpenMAIC](02_agent_runtimes_and_harnesses/openmaic.md)
* **`#whiteboard`** (1): [Whiteboard](06_developer_tools_and_apps/whiteboard.md)
* **`#wireguard`** (1): [FQ-Book](05_security_osint_and_guardrails/fq-book.md)
* **`#workflow-automation`** (2): [Evenfire](02_agent_runtimes_and_harnesses/evenfire.md), [Paperclip](02_agent_runtimes_and_harnesses/paperclip.md)
* **`#world-model`** (1): [Utopia](03_knowledge_graphs_and_ontologies/utopia.md)
* **`#yagni`** (1): [Ponytail](02_agent_runtimes_and_harnesses/ponytail.md)
* **`#youtube`** (1): [Agent-Reach](02_agent_runtimes_and_harnesses/agent-reach.md)
* **`#zed`** (1): [Disktree](06_developer_tools_and_apps/disktree.md)
* **`#zero-api-fees`** (1): [Agent-Reach](02_agent_runtimes_and_harnesses/agent-reach.md)
* **`#zero-trust`** (2): [Docker Agent](02_agent_runtimes_and_harnesses/docker-agent.md), [TCB & Reference Monitor](05_security_osint_and_guardrails/tcb-agent-security.md)

---
*Сгенерировано автоматически: 2026-10-10 | Antigravity Knowledge Base*