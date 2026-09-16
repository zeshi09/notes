# 🧭 База знаний и заметок по AI-инженерии, агентам и софту

> **Каталог заметок по передовым GitHub репозиториям и архитектурным паттернам.**
> Структура организована по тематическим категориям с поддержкой YAML Frontmatter тегирования (совместимо с Obsidian, Logseq, VS Code).

🎯 **Главный стратегический документ:** [🚀 Capstone Roadmap: Превращение базы знаний в автономную исследовательскую лабораторию](00_strategy_and_roadmaps/capstone-engineering-roadmap.md)
🛡️ **Архитектурный стандарт безопасности агентов:** [🛡️ TCB & Reference Monitor: Полное руководство](05_security_osint_and_guardrails/tcb-agent-security.md)
🔀 **Архитектура шлюзов и брокеров тулов:** [🔀 Архитектура Tool Broker & Execution Blocker](02_agent_runtimes_and_harnesses/tool-broker-architecture.md)

---

## 📂 Тематические категории

### 🚀 00. Стратегия, дорожные карты и Capstone-проекты
*Сквозные роадмапы превращения базы знаний в практическую инженерную экспертизу и работающие продукты.*

| Заметка | Репозиторий | Звёзды | Теги |
| :--- | :--- | :--- | :--- |
| 📄 **[Capstone Roadmap: Как превратить базу знаний в персональную исследовательскую лабораторию](00_strategy_and_roadmaps/capstone-engineering-roadmap.md)** | [knowledge-base/strategy](local://knowledge-base/strategy) | `Master-Plan` | `#learning-roadmap` `#capstone-project` `#ai-engineering` `#autonomous-research` `#strategy` `#system-architecture` |

### 🧠 01. Архитектура LLM и обучение моделей с нуля
*Трансформеры с нуля, модели рассуждения (DeepSeek-R1/GRPO), системный дизайн AI-инфраструктуры (AI Infra Book Ли Боцзе), ультралегкие LLM (MiniMind), фундаментальные курсы (Dive into LLMs), полностековые дорожные карты и инженерные туториалы (LLM Master) и сквозная AI-инженерия.*

| Заметка | Репозиторий | Звёзды | Теги |
| :--- | :--- | :--- | :--- |
| 📄 **[LLMs from Scratch (Себастьян Рашка)](01_llm_architecture_and_training/LLMs-from-scratch.md)** | [rasbt/LLMs-from-scratch](https://github.com/rasbt/LLMs-from-scratch) | `47.5k+` | `#llm` `#pytorch` `#transformers` `#from-scratch` `#education` `#deep-learning` |
| 📄 **[AI Engineering from Scratch (Рохит Гумаре: 511 уроков, 20 фаз)](01_llm_architecture_and_training/ai-engineering-from-scratch.md)** | [blackzeshi/Git/ai-engineering-from-scratch](https://github.com/blackzeshi/Git/ai-engineering-from-scratch) | `Local / 14k+` | `#ai-engineering` `#roadmap` `#mcp` `#vllm` `#grpo` `#rag` `#agent-orchestration` |
| 📄 **[AI Infra Book: Количественный анализ и системный дизайн AI-инфраструктуры (Ли Боцзе / Bojie Li)](01_llm_architecture_and_training/ai-infra-book.md)** | [bojieli/ai-infra-book](https://github.com/bojieli/ai-infra-book) | `2.2k+` | `#ai-infra-book` `#ai-infrastructure` `#system-design` `#hardware-constraints` `#kv-cache` `#roofline-model` `#distributed-inference` `#distributed-training` `#rdma` `#vllm` `#bojie-li` `#open-source-book` |
| 📄 **[Dive into LLMs (动手学大模型): Практический курс инженерии больших языковых моделей](01_llm_architecture_and_training/dive-into-llms.md)** | [Lordog/dive-into-llms](https://github.com/Lordog/dive-into-llms) | `51.3k+` | `#llm` `#transformers` `#pretraining` `#sft` `#lora` `#rlhf` `#dpo` `#quantization` `#vllm` `#deep-learning` `#jupyter` |
| 📄 **[LLM-Master: Полностековая инженерная дорожная карта и учебник по LLM, RAG и Agent](01_llm_architecture_and_training/llm-master.md)** | [youngyangyang04/llm-master](https://github.com/youngyangyang04/llm-master) | `400+` | `#llm-master` `#llm-roadmap` `#prompt-engineering` `#rag` `#ai-agents` `#mcp` `#fine-tuning` `#vllm` `#transformers` `#interview-prep` `#system-design` |
| 📄 **[MiniMind: Обучение собственной LLM (64M) с нуля за 2 часа](01_llm_architecture_and_training/minimind.md)** | [jingyaogong/minimind](https://github.com/jingyaogong/minimind) | `56.7k+` | `#llm` `#pretraining` `#sft` `#lora` `#dpo` `#lightweight-models` `#pytorch` |
| 📄 **[Reasoning from Scratch (Себастьян Рашка: DeepSeek-R1, GRPO, RLVR)](01_llm_architecture_and_training/reasoning-from-scratch.md)** | [rasbt/reasoning-from-scratch](https://github.com/rasbt/reasoning-from-scratch) | `18.2k+` | `#reasoning` `#deepseek-r1` `#grpo` `#rlvr` `#reinforcement-learning` `#inference-scaling` |

### 🤖 02. Агентные рантаймы, харнесы и оркестрация
*Фундаментальные учебники по архитектуре агентов (AI Agent Book Ли Боцзе), гибридное код-ревью (Open Code Review от Alibaba), защищенные реестры навыков (Agent-Skills), инженерия агентных сред (Harness Engineering), архитектура брокеров тулов (Tool Broker & Blocker), интернет-шлюзы (Agent-Reach), суб-миллисекундные микро-VM (ZeroBoot), self-hosted песочницы (Dormice), вайб-кодинг (M3E Canvas), гибридный поиск (zvec-grep), микро-интерпретаторы (Monty), дизайн-манифесты (DESIGN.md), VCS (Atlas), песочницы на Rust (Arcbox).*

| Заметка | Репозиторий | Звёзды | Теги |
| :--- | :--- | :--- | :--- |
| 📄 **[Agent-Reach: Универсальный интернет-шлюз и сборщик контента для AI-агентов с нулевыми затратами на API](02_agent_runtimes_and_harnesses/agent-reach.md)** | [Panniantong/Agent-Reach](https://github.com/Panniantong/Agent-Reach) | `79.9k+` | `#agent-reach` `#web-scraping` `#agent-eyes` `#multi-platform` `#zero-api-fees` `#fallback-routing` `#twitter` `#reddit` `#youtube` `#bilibili` `#github` `#mcp` |
| 📄 **[Agent-Skills: Защищенный и верифицированный реестр навыков для кодинг-агентов (Tech Leads Club)](02_agent_runtimes_and_harnesses/agent-skills.md)** | [tech-leads-club/agent-skills](https://github.com/tech-leads-club/agent-skills) | `5.9k+` | `#agent-skills` `#skill-registry` `#antigravity` `#claude-code` `#cursor` `#supply-chain-security` `#verified-skills` `#mcp` `#spec-driven` `#typescript` `#snyk-agent-scan` |
| 📄 **[AI Agent Book: Архитектура, инженерия харнесов и промышленная практика (Ли Боцзе / Bojie Li)](02_agent_runtimes_and_harnesses/ai-agent-book.md)** | [bojieli/ai-agent-book](https://github.com/bojieli/ai-agent-book) | `46.2k+` | `#ai-agent-book` `#harness-engineering` `#context-engineering` `#mcp` `#coding-agents` `#multi-agent` `#agent-evals` `#post-training` `#continuous-evolution` `#kv-cache` `#bojie-li` `#open-source-book` |
| 📄 **[ArcBox: Изолированные контейнеры и микро-VM для AI-Агентов на Rust](02_agent_runtimes_and_harnesses/arcbox.md)** | [arcboxlabs/arcbox](https://github.com/arcboxlabs/arcbox) | `1.9k+` | `#sandboxing` `#rust` `#micro-vm` `#containers` `#oci` `#agent-security` |
| 📄 **[Atlas: Система контроля версий (VCS) для параллельных AI-агентов на Rust](02_agent_runtimes_and_harnesses/atlas.md)** | [pacifio/atlas](https://github.com/pacifio/atlas) | `2.1k+` | `#vcs` `#ai-agents` `#rust` `#tree-sitter` `#ast-merge` `#source-control` |
| 📄 **[Awesome DESIGN.md: Спецификации дизайн-систем для AI-агентов кодинга](02_agent_runtimes_and_harnesses/awesome-design-md.md)** | [VoltAgent/awesome-design-md](https://github.com/VoltAgent/awesome-design-md) | `113.5k+` | `#design-systems` `#ai-coding` `#claude-code` `#cursor` `#codex` `#ui-ux` `#prompt-engineering` `#frontend` |
| 📄 **[Diagram Design: 39 журнальных типов диаграмм на чистом HTML+SVG для AI-агентов](02_agent_runtimes_and_harnesses/diagram-design.md)** | [cathrynlavery/diagram-design](https://github.com/cathrynlavery/diagram-design) | `30.2k+` | `#data-visualization` `#diagrams` `#html` `#svg` `#ai-agents` `#claude-code` `#codex` `#no-mermaid` |
| 📄 **[Dormice: «SQLite среди песочниц» — Self-Hosted долгоживущие песочницы для AI-агентов](02_agent_runtimes_and_harnesses/dormice.md)** | [BitMiracle-AI/Dormice](https://github.com/BitMiracle-AI/Dormice) | `1.0k+` | `#agent-sandbox` `#self-hosted` `#e2b-compatible` `#gvisor` `#docker` `#typescript` `#idle-zero-cost` |
| 📄 **[i-have-adhd: Скилл и поведенческий слой для кодинг-агентов (ADHD-friendly output без «воды»)](02_agent_runtimes_and_harnesses/i-have-adhd.md)** | [ayghri/i-have-adhd](https://github.com/ayghri/i-have-adhd) | `42.5k+` | `#agent-skills` `#prompt-engineering` `#ux` `#productivity` `#claude-code` `#cursor` `#codex` `#adhd` `#formatting` |
| 📄 **[Learn Harness Engineering (Курс WalkingLabs: 14 лекций, 8 проектов)](02_agent_runtimes_and_harnesses/learn-harness-engineering.md)** | [walkinglabs/learn-harness-engineering](https://github.com/walkinglabs/learn-harness-engineering) | `12.8k+` | `#harness-engineering` `#ai-agents` `#mcp` `#agent-architecture` `#audit-harness` |
| 📄 **[M3E Canvas: Браузерный конструктор экранов Material 3 Expressive с генерацией промптов для вайб-кодинга](02_agent_runtimes_and_harnesses/m3e-canvas.md)** | [lnkiai/m3e-canvas](https://github.com/lnkiai/m3e-canvas) | `880+` | `#vibe-coding` `#prompt-engineering` `#ui-ux` `#material-design` `#react` `#prototyping` `#ai-coding` `#canvas` |
| 📄 **[Monty: Минималистичный и безопасный интерпретатор Python на Rust для AI-агентов](02_agent_runtimes_and_harnesses/monty.md)** | [pydantic/monty](https://github.com/pydantic/monty) | `8.2k+` | `#python-interpreter` `#rust` `#agent-sandbox` `#code-mode` `#pydantic` `#programmatic-tool-calling` `#security` `#micro-runtime` |
| 📄 **[Open Code Review: Промышленный гибридный инструмент код-ревью от Alibaba (Deterministic Engineering × Agent)](02_agent_runtimes_and_harnesses/open-code-review.md)** | [alibaba/open-code-review](https://github.com/alibaba/open-code-review) | `25.2k+` | `#open-code-review` `#alibaba` `#code-review` `#deterministic-engineering` `#agent-hybrid` `#ast-analysis` `#line-level-precision` `#token-efficiency` `#git-diff` `#security-rules` `#go` `#aacr-bench` |
| 📄 **[OpenMAIC: Мульти-агентная интерактивная аудитория (Цинхуа)](02_agent_runtimes_and_harnesses/openmaic.md)** | [THU-MAIC/OpenMAIC](https://github.com/THU-MAIC/OpenMAIC) | `28.9k+` | `#multi-agent` `#education` `#typescript` `#webrtc` `#interactive-learning` |
| 📄 **[SoL-Pi: Оптимизация агентных харнесов и исследовательских циклов от Nvidia Research](02_agent_runtimes_and_harnesses/sol-pi.md)** | [NVlabs/SoL-Pi](https://github.com/NVlabs/SoL-Pi) | `1.3k+` | `#nvidia` `#agent-harness` `#efficiency` `#context-compression` `#action-fusion` `#observation-pack` `#pi-agent` `#auto-research` `#token-diet` |
| 📄 **[Архитектура Tool Broker & Execution Blocker: Проектирование шлюзов вызова и защиты инструментов AI-агентов](02_agent_runtimes_and_harnesses/tool-broker-architecture.md)** | [agent-architecture/tool-broker](local://agent-architecture/tool-broker) | `Master-Architecture` | `#tool-broker` `#tool-gateway` `#mcp-router` `#agent-runtime` `#tool-rag` `#lethal-trifecta` `#loop-breaker` `#security` `#credential-offloading` |
| 📄 **[ZeroBoot: Суб-миллисекундные песочницы микро-VM для AI-агентов на чистом Rust](02_agent_runtimes_and_harnesses/zeroboot.md)** | [zerobootdev/zeroboot](https://github.com/zerobootdev/zeroboot) | `2.4k+` | `#agent-sandbox` `#rust` `#micro-vm` `#copy-on-write` `#virtualization` `#code-execution` `#high-performance` |
| 📄 **[zvec-grep (zg): Локальный гибридный поиск по кодовой базе для людей и AI-агентов](02_agent_runtimes_and_harnesses/zvec-grep.md)** | [zvec-ai/zvec-grep](https://github.com/zvec-ai/zvec-grep) | `1.8k+` | `#search` `#local-first` `#semantic-search` `#vector-search` `#ai-agents` `#code-search` `#bm25` `#hybrid-search` |

### 🏛️ 03. Графы знаний, контекст и онтологии
*Графовая инфраструктура контекста (Semantica AGI) и Enterprise World Model воркбенчи на Rust (Utopia).*

| Заметка | Репозиторий | Звёзды | Теги |
| :--- | :--- | :--- | :--- |
| 📄 **[Semantica AGI: Графовая инфраструктура контекста и подотчетности](03_knowledge_graphs_and_ontologies/semantica.md)** | [semantica-agi/semantica](https://github.com/semantica-agi/semantica) | `11.4k+` | `#knowledge-graphs` `#prov-o` `#decision-intelligence` `#datalog` `#shacl` `#rete` |
| 📄 **[Utopia: Open-Source Enterprise World Model & Ontology Workbench](03_knowledge_graphs_and_ontologies/utopia.md)** | [deeplethe/utopia](https://github.com/deeplethe/utopia) | `1.3k+` | `#ontologies` `#world-model` `#rust` `#local-first` `#mcp` `#knowledge-graphs` |

### 🔬 04. Автономные исследования и AI for Science
*Автономные исследовательские харнесы (Hyperresearch), академические скиллы полного цикла (Academic Research Skills), библиотеки специализированных тулов (165+ скиллов) и автономные лаборатории (PRAXIST).*

| Заметка | Репозиторий | Звёзды | Теги |
| :--- | :--- | :--- | :--- |
| 📄 **[Academic Research Skills: Полный цикл научных исследований для Claude Code](04_scientific_research_and_discovery/academic-research-skills.md)** | [Imbad0202/academic-research-skills](https://github.com/Imbad0202/academic-research-skills) | `45.5k+` | `#academic-research` `#claude-code` `#scientific-writing` `#peer-review` `#latex` `#citation-audit` `#socratic-planning` |
| 📄 **[Hyperresearch: Автономный Deep Research харнес с самообучающимся хранилищем и 16-шаговым конвейером](04_scientific_research_and_discovery/hyperresearch.md)** | [jordan-gibbs/hyperresearch](https://github.com/jordan-gibbs/hyperresearch) | `2.9k+` | `#deep-research` `#academic-research` `#claude-code` `#agents` `#mcp` `#knowledge-vault` `#web-scraping` `#peer-review` `#citation-verification` |
| 📄 **[PRAXIST: Автономный исследовательский R&D фреймворк](04_scientific_research_and_discovery/praxist.md)** | [sapientinc/PRAXIST](https://github.com/sapientinc/PRAXIST) | `5.4k+` | `#autonomous-research` `#evolutionary-search` `#r-and-d` `#evidence-ledger` `#arxiv` |
| 📄 **[Scientific Agent Skills (K-Dense AI: 165 научных навыков и 100+ баз)](04_scientific_research_and_discovery/scientific-agent-skills.md)** | [K-Dense-AI/scientific-agent-skills](https://github.com/K-Dense-AI/scientific-agent-skills) | `41.3k+` | `#ai-science` `#agent-skills` `#biology` `#chemistry` `#drug-discovery` `#pubmed` `#alphafold` |

### 🛡️ 05. Кибербезопасность, OSINT и тестирование барьеров
*AI-Native AppSec экосистема и агентные MITM-прокси (Ghost Security: Reaper, Poltergeist, Wraith), анатомия ядра Linux и харденинг контейнеров (Linux Insides & NCC Group), шестифазный агентный аудит уязвимостей от Cloudflare (Security Audit Skill), архитектура доверенных вычислений агентов (TCB & Reference Monitor), headless security воркбенчи на Rust (HuntProxy), наступательные агентные навыки (Claude-Red), агентные файрволы (Pipelock), supply-chain сканеры (SkillSpector), Egress Anti-SSRF (Smokescreen), аудит шлюзов (API Relay Audit), системные промпты (CL4R1T4S).*

| Заметка | Репозиторий | Звёзды | Теги |
| :--- | :--- | :--- | :--- |
| 📄 **[CL4R1T4S: База утекших системных промптов ведущих AI-моделей и агентов](05_security_osint_and_guardrails/CL4R1T4S.md)** | [elder-plinius/CL4R1T4S](https://github.com/elder-plinius/CL4R1T4S) | `48.4k+` | `#system-prompts` `#transparency` `#red-teaming` `#prompt-engineering` `#guardrails` `#ai-security` `#jailbreak-analysis` |
| 📄 **[API Relay Audit: Локальный аудит безопасности LLM-прокси, API-релеев и подмены моделей](05_security_osint_and_guardrails/api-relay-audit.md)** | [toby-bridges/api-relay-audit](https://github.com/toby-bridges/api-relay-audit) | `820+` | `#llm-security` `#api-proxy` `#audit` `#prompt-injection` `#model-substitution` `#sse-anomalies` `#tool-call-tampering` |
| 📄 **[Claude-Red: Кураторская библиотека наступательных навыков (Offensive Security Skills) для Claude](05_security_osint_and_guardrails/claude-red.md)** | [SnailSploit/Claude-Red](https://github.com/SnailSploit/Claude-Red) | `3.7k+` | `#claude-skills` `#red-teaming` `#offensive-security` `#skill-md` `#prompt-engineering` `#pen-testing` `#exploit-development` `#edr-evasion` `#vulnerability-research` `#authorized-testing` |
| 📄 **[Ghost Security: Экосистема AI-Native AppSec инструментов и агентных MITM-прокси (Reaper, Poltergeist, Wraith)](05_security_osint_and_guardrails/ghost-security.md)** | [ghostsecurity](https://github.com/ghostsecurity) | `1.3k+ (всего)` | `#ghost-security` `#reaper` `#appsec` `#ai-agents` `#mitm-proxy` `#dast` `#sast` `#sca` `#mcp` `#claude-code` `#go` `#security-audit` |
| 📄 **[GPT-5.6 Instruct: Red Teaming и стресс-тестирование агентных систем](05_security_osint_and_guardrails/gpt-5.6-instruct.md)** | [MDX-Tom/gpt-5.6-instruct](https://github.com/MDX-Tom/gpt-5.6-instruct) | `7.1k+` | `#security` `#red-teaming` `#guardrails` `#alignment` `#jailbreak-testing` `#codex-cli` |
| 📄 **[HuntProxy: Headless перехватывающий веб-прокси и Security Workbench для AI-агентов на Rust](05_security_osint_and_guardrails/huntproxy.md)** | [BehiSecc/HuntProxy](https://github.com/BehiSecc/HuntProxy) | `175+` | `#huntproxy` `#rust` `#agent-proxy` `#mcp` `#security-workbench` `#burp-alternative` `#headless-browser` `#fuzzing` `#sitemap-discovery` `#web-security` `#ai-pentesting` |
| 📄 **[Анатомия ядра Linux и харденинг контейнеров: От Linux Insides до NCC Group](05_security_osint_and_guardrails/linux-kernel-and-container-hardening.md)** | [0xAX/linux-insides](https://github.com/0xAX/linux-insides) | `33.5k+` | `#linux-kernel` `#linux-insides` `#container-security` `#ncc-group` `#namespaces` `#cgroups` `#capabilities` `#seccomp-bpf` `#kernel-hardening` `#apparmor` `#selinux` `#sandboxing` |
| 📄 **[Pipelock: Open-Source файрвол для AI-агентов, MCP-серверов и верифицируемого Egress-контроля](05_security_osint_and_guardrails/pipelock.md)** | [luckyPipewrench/pipelock](https://github.com/luckyPipewrench/pipelock) | `830+` | `#agent-firewall` `#egress-control` `#mcp-security` `#ssrf-prevention` `#prompt-injection` `#tcb` `#mediator-receipts` `#go` `#cncf` |
| 📄 **[Cloudflare Security Audit Skill: Шестифазный агентный аудит уязвимостей с верификацией](05_security_osint_and_guardrails/security-audit-skill.md)** | [cloudflare/security-audit-skill](https://github.com/cloudflare/security-audit-skill) | `4.6k+` | `#security-audit-skill` `#cloudflare` `#agent-skills` `#vulnerability-assessment` `#security-audit` `#sarif` `#json-findings` `#prompt-injection` `#claude-code` `#adversarial-verification` `#sandboxing` |
| 📄 **[SkillSpector: Сканер безопасности и Supply-Chain аудитор агентных навыков (NVIDIA)](05_security_osint_and_guardrails/skillspector.md)** | [NVIDIA/SkillSpector](https://github.com/NVIDIA/SkillSpector) | `16.1k+` | `#agent-security` `#supply-chain` `#skill-scanner` `#prompt-injection` `#claude-code` `#mcp` `#nvidia` `#static-analysis` |
| 📄 **[Smokescreen: HTTP CONNECT прокси от Stripe для изоляции Egress-трафика и защиты от SSRF](05_security_osint_and_guardrails/smokescreen.md)** | [stripe/smokescreen](https://github.com/stripe/smokescreen) | `1.3k+` | `#egress-proxy` `#ssrf-prevention` `#stripe` `#go` `#network-security` `#tcb` `#dns-rebinding` `#acl` |
| 📄 **[TCB & Reference Monitor: Полное руководство по архитектуре доверенной базы вычислений для автономных AI-агентов](05_security_osint_and_guardrails/tcb-agent-security.md)** | [ai_pentester/tcb](local://ai_pentester/tcb) | `Master-Architecture` | `#tcb` `#trusted-computing-base` `#reference-monitor` `#agent-security` `#fail-closed` `#ssrf-prevention` `#prompt-injection` `#zero-trust` `#sandboxing` `#secret-broker` |
| 📄 **[User Scanner: Профессиональный OSINT-комбайн по Email и Никнеймам](05_security_osint_and_guardrails/user-scanner.md)** | [kaifcodec/user-scanner](https://github.com/kaifcodec/user-scanner) | `4.5k+` | `#osint` `#security` `#digital-footprint` `#email-recon` `#username-scanner` `#python` |

### ⚡ 06. Инструменты разработчика, архитектура и нативный софт
*Агентная автоматизация реального браузера без перехвата фокуса (Tencent BrowserSkill), визуальная архитектура распределенных систем (System Design 101), невидимые браузерные агенты с MCP (AIHawk), краулеры и экстракторы для LLM (Crawl4AI), headless-браузеры для AI-агентов (Obscura) и легковесные нативные десктопные клиенты (Fastpotify).*

| Заметка | Репозиторий | Звёзды | Теги |
| :--- | :--- | :--- | :--- |
| 📄 **[AIHawk: Скрытный антибот-браузер и агент веб-автоматизации с поддержкой MCP (Undetected Browsing)](06_developer_tools_and_apps/ai-hawk.md)** | [feder-cr/AIHawk](https://github.com/feder-cr/AIHawk) | `31.5k+` | `#ai-hawk` `#stealth-browser` `#anti-detect` `#anti-bot-bypass` `#mcp` `#browser-agent` `#web-automation` `#computer-use` `#playwright` `#cloudflare-bypass` `#python` |
| 📄 **[Tencent BrowserSkill: Агентная автоматизация реального браузера без перехвата фокуса (Rust + Chromium Extension)](06_developer_tools_and_apps/browserskill.md)** | [Tencent/BrowserSkill](https://github.com/Tencent/BrowserSkill) | `2.8k+` | `#browserskill` `#tencent` `#browser-automation` `#browser-agent` `#rust` `#bsk-cli` `#chromium-extension` `#human-in-the-loop` `#tab-borrowing` `#claude-code` `#cursor` |
| 📄 **[Crawl4AI: Высокопроизводительный открытый веб-краулер и парсер для LLM, RAG и AI-агентов](06_developer_tools_and_apps/crawl4ai.md)** | [unclecode/crawl4ai](https://github.com/unclecode/crawl4ai) | `82.8k+` | `#crawl4ai` `#web-crawler` `#web-scraping` `#llm-ready` `#markdown` `#rag` `#ai-agents` `#playwright` `#structured-extraction` `#bm25` `#docker` |
| 📄 **[Fastpotify: Нативный и молниеносный клиент Spotify на Rust](06_developer_tools_and_apps/fastpotify.md)** | [crmne/fastpotify](https://github.com/crmne/fastpotify) | `1.3k+` | `#rust` `#desktop-app` `#spotify` `#egui` `#librespot` `#audio-player` |
| 📄 **[Obscura: Высокопроизводительный Headless-Браузер для AI-Агентов на Rust](06_developer_tools_and_apps/obscura.md)** | [h4ckf0r0day/obscura](https://github.com/h4ckf0r0day/obscura) | `23.3k+` | `#headless-browser` `#rust` `#anti-bot-bypass` `#accessibility-tree` `#web-scraping` |
| 📄 **[System Design 101: Визуальная энциклопедия архитектуры распределенных систем (ByteByteGo)](06_developer_tools_and_apps/system-design-101.md)** | [ByteByteGoHq/system-design-101](https://github.com/ByteByteGoHq/system-design-101) | `88.6k+` | `#system-design` `#distributed-systems` `#architecture` `#microservices` `#databases` `#caching` `#bytebytego` `#visual-guide` |

---

## 🏷️ Облако тегов (Tag Index)

* **`#aacr-bench`** (1): [Open Code Review](02_agent_runtimes_and_harnesses/open-code-review.md)
* **`#academic-research`** (2): [Academic Research Skills](04_scientific_research_and_discovery/academic-research-skills.md), [Hyperresearch](04_scientific_research_and_discovery/hyperresearch.md)
* **`#accessibility-tree`** (1): [Obscura](06_developer_tools_and_apps/obscura.md)
* **`#acl`** (1): [Smokescreen](05_security_osint_and_guardrails/smokescreen.md)
* **`#action-fusion`** (1): [SoL-Pi](02_agent_runtimes_and_harnesses/sol-pi.md)
* **`#adhd`** (1): [i-have-adhd](02_agent_runtimes_and_harnesses/i-have-adhd.md)
* **`#adversarial-verification`** (1): [Cloudflare Security Audit Skill](05_security_osint_and_guardrails/security-audit-skill.md)
* **`#agent-architecture`** (1): [Learn Harness Engineering (Курс WalkingLabs](02_agent_runtimes_and_harnesses/learn-harness-engineering.md)
* **`#agent-evals`** (1): [AI Agent Book](02_agent_runtimes_and_harnesses/ai-agent-book.md)
* **`#agent-eyes`** (1): [Agent-Reach](02_agent_runtimes_and_harnesses/agent-reach.md)
* **`#agent-firewall`** (1): [Pipelock](05_security_osint_and_guardrails/pipelock.md)
* **`#agent-harness`** (1): [SoL-Pi](02_agent_runtimes_and_harnesses/sol-pi.md)
* **`#agent-hybrid`** (1): [Open Code Review](02_agent_runtimes_and_harnesses/open-code-review.md)
* **`#agent-orchestration`** (1): [AI Engineering from Scratch (Рохит Гумаре](01_llm_architecture_and_training/ai-engineering-from-scratch.md)
* **`#agent-proxy`** (1): [HuntProxy](05_security_osint_and_guardrails/huntproxy.md)
* **`#agent-reach`** (1): [Agent-Reach](02_agent_runtimes_and_harnesses/agent-reach.md)
* **`#agent-runtime`** (1): [Архитектура Tool Broker & Execution Blocker](02_agent_runtimes_and_harnesses/tool-broker-architecture.md)
* **`#agent-sandbox`** (3): [Dormice](02_agent_runtimes_and_harnesses/dormice.md), [Monty](02_agent_runtimes_and_harnesses/monty.md), [ZeroBoot](02_agent_runtimes_and_harnesses/zeroboot.md)
* **`#agent-security`** (3): [ArcBox](02_agent_runtimes_and_harnesses/arcbox.md), [SkillSpector](05_security_osint_and_guardrails/skillspector.md), [TCB & Reference Monitor](05_security_osint_and_guardrails/tcb-agent-security.md)
* **`#agent-skills`** (4): [Agent-Skills](02_agent_runtimes_and_harnesses/agent-skills.md), [i-have-adhd](02_agent_runtimes_and_harnesses/i-have-adhd.md), [Scientific Agent Skills (K-Dense AI](04_scientific_research_and_discovery/scientific-agent-skills.md), [Cloudflare Security Audit Skill](05_security_osint_and_guardrails/security-audit-skill.md)
* **`#agents`** (1): [Hyperresearch](04_scientific_research_and_discovery/hyperresearch.md)
* **`#ai-agent-book`** (1): [AI Agent Book](02_agent_runtimes_and_harnesses/ai-agent-book.md)
* **`#ai-agents`** (7): [LLM-Master](01_llm_architecture_and_training/llm-master.md), [Atlas](02_agent_runtimes_and_harnesses/atlas.md), [Diagram Design](02_agent_runtimes_and_harnesses/diagram-design.md), [Learn Harness Engineering (Курс WalkingLabs](02_agent_runtimes_and_harnesses/learn-harness-engineering.md), [zvec-grep (zg)](02_agent_runtimes_and_harnesses/zvec-grep.md), [Ghost Security](05_security_osint_and_guardrails/ghost-security.md), [Crawl4AI](06_developer_tools_and_apps/crawl4ai.md)
* **`#ai-coding`** (2): [Awesome DESIGN.md](02_agent_runtimes_and_harnesses/awesome-design-md.md), [M3E Canvas](02_agent_runtimes_and_harnesses/m3e-canvas.md)
* **`#ai-engineering`** (2): [Capstone Roadmap](00_strategy_and_roadmaps/capstone-engineering-roadmap.md), [AI Engineering from Scratch (Рохит Гумаре](01_llm_architecture_and_training/ai-engineering-from-scratch.md)
* **`#ai-hawk`** (1): [AIHawk](06_developer_tools_and_apps/ai-hawk.md)
* **`#ai-infra-book`** (1): [AI Infra Book](01_llm_architecture_and_training/ai-infra-book.md)
* **`#ai-infrastructure`** (1): [AI Infra Book](01_llm_architecture_and_training/ai-infra-book.md)
* **`#ai-pentesting`** (1): [HuntProxy](05_security_osint_and_guardrails/huntproxy.md)
* **`#ai-science`** (1): [Scientific Agent Skills (K-Dense AI](04_scientific_research_and_discovery/scientific-agent-skills.md)
* **`#ai-security`** (1): [CL4R1T4S](05_security_osint_and_guardrails/CL4R1T4S.md)
* **`#alibaba`** (1): [Open Code Review](02_agent_runtimes_and_harnesses/open-code-review.md)
* **`#alignment`** (1): [GPT-5.6 Instruct](05_security_osint_and_guardrails/gpt-5.6-instruct.md)
* **`#alphafold`** (1): [Scientific Agent Skills (K-Dense AI](04_scientific_research_and_discovery/scientific-agent-skills.md)
* **`#anti-bot-bypass`** (2): [AIHawk](06_developer_tools_and_apps/ai-hawk.md), [Obscura](06_developer_tools_and_apps/obscura.md)
* **`#anti-detect`** (1): [AIHawk](06_developer_tools_and_apps/ai-hawk.md)
* **`#antigravity`** (1): [Agent-Skills](02_agent_runtimes_and_harnesses/agent-skills.md)
* **`#api-proxy`** (1): [API Relay Audit](05_security_osint_and_guardrails/api-relay-audit.md)
* **`#apparmor`** (1): [Анатомия ядра Linux и харденинг контейнеров](05_security_osint_and_guardrails/linux-kernel-and-container-hardening.md)
* **`#appsec`** (1): [Ghost Security](05_security_osint_and_guardrails/ghost-security.md)
* **`#architecture`** (1): [System Design 101](06_developer_tools_and_apps/system-design-101.md)
* **`#arxiv`** (1): [PRAXIST](04_scientific_research_and_discovery/praxist.md)
* **`#ast-analysis`** (1): [Open Code Review](02_agent_runtimes_and_harnesses/open-code-review.md)
* **`#ast-merge`** (1): [Atlas](02_agent_runtimes_and_harnesses/atlas.md)
* **`#audio-player`** (1): [Fastpotify](06_developer_tools_and_apps/fastpotify.md)
* **`#audit`** (1): [API Relay Audit](05_security_osint_and_guardrails/api-relay-audit.md)
* **`#audit-harness`** (1): [Learn Harness Engineering (Курс WalkingLabs](02_agent_runtimes_and_harnesses/learn-harness-engineering.md)
* **`#authorized-testing`** (1): [Claude-Red](05_security_osint_and_guardrails/claude-red.md)
* **`#auto-research`** (1): [SoL-Pi](02_agent_runtimes_and_harnesses/sol-pi.md)
* **`#autonomous-research`** (2): [Capstone Roadmap](00_strategy_and_roadmaps/capstone-engineering-roadmap.md), [PRAXIST](04_scientific_research_and_discovery/praxist.md)
* **`#bilibili`** (1): [Agent-Reach](02_agent_runtimes_and_harnesses/agent-reach.md)
* **`#biology`** (1): [Scientific Agent Skills (K-Dense AI](04_scientific_research_and_discovery/scientific-agent-skills.md)
* **`#bm25`** (2): [zvec-grep (zg)](02_agent_runtimes_and_harnesses/zvec-grep.md), [Crawl4AI](06_developer_tools_and_apps/crawl4ai.md)
* **`#bojie-li`** (2): [AI Infra Book](01_llm_architecture_and_training/ai-infra-book.md), [AI Agent Book](02_agent_runtimes_and_harnesses/ai-agent-book.md)
* **`#browser-agent`** (2): [AIHawk](06_developer_tools_and_apps/ai-hawk.md), [Tencent BrowserSkill](06_developer_tools_and_apps/browserskill.md)
* **`#browser-automation`** (1): [Tencent BrowserSkill](06_developer_tools_and_apps/browserskill.md)
* **`#browserskill`** (1): [Tencent BrowserSkill](06_developer_tools_and_apps/browserskill.md)
* **`#bsk-cli`** (1): [Tencent BrowserSkill](06_developer_tools_and_apps/browserskill.md)
* **`#burp-alternative`** (1): [HuntProxy](05_security_osint_and_guardrails/huntproxy.md)
* **`#bytebytego`** (1): [System Design 101](06_developer_tools_and_apps/system-design-101.md)
* **`#caching`** (1): [System Design 101](06_developer_tools_and_apps/system-design-101.md)
* **`#canvas`** (1): [M3E Canvas](02_agent_runtimes_and_harnesses/m3e-canvas.md)
* **`#capabilities`** (1): [Анатомия ядра Linux и харденинг контейнеров](05_security_osint_and_guardrails/linux-kernel-and-container-hardening.md)
* **`#capstone-project`** (1): [Capstone Roadmap](00_strategy_and_roadmaps/capstone-engineering-roadmap.md)
* **`#cgroups`** (1): [Анатомия ядра Linux и харденинг контейнеров](05_security_osint_and_guardrails/linux-kernel-and-container-hardening.md)
* **`#chemistry`** (1): [Scientific Agent Skills (K-Dense AI](04_scientific_research_and_discovery/scientific-agent-skills.md)
* **`#chromium-extension`** (1): [Tencent BrowserSkill](06_developer_tools_and_apps/browserskill.md)
* **`#citation-audit`** (1): [Academic Research Skills](04_scientific_research_and_discovery/academic-research-skills.md)
* **`#citation-verification`** (1): [Hyperresearch](04_scientific_research_and_discovery/hyperresearch.md)
* **`#claude-code`** (10): [Agent-Skills](02_agent_runtimes_and_harnesses/agent-skills.md), [Awesome DESIGN.md](02_agent_runtimes_and_harnesses/awesome-design-md.md), [Diagram Design](02_agent_runtimes_and_harnesses/diagram-design.md), [i-have-adhd](02_agent_runtimes_and_harnesses/i-have-adhd.md), [Academic Research Skills](04_scientific_research_and_discovery/academic-research-skills.md), [Hyperresearch](04_scientific_research_and_discovery/hyperresearch.md), [Ghost Security](05_security_osint_and_guardrails/ghost-security.md), [Cloudflare Security Audit Skill](05_security_osint_and_guardrails/security-audit-skill.md), [SkillSpector](05_security_osint_and_guardrails/skillspector.md), [Tencent BrowserSkill](06_developer_tools_and_apps/browserskill.md)
* **`#claude-skills`** (1): [Claude-Red](05_security_osint_and_guardrails/claude-red.md)
* **`#cloudflare`** (1): [Cloudflare Security Audit Skill](05_security_osint_and_guardrails/security-audit-skill.md)
* **`#cloudflare-bypass`** (1): [AIHawk](06_developer_tools_and_apps/ai-hawk.md)
* **`#cncf`** (1): [Pipelock](05_security_osint_and_guardrails/pipelock.md)
* **`#code-execution`** (1): [ZeroBoot](02_agent_runtimes_and_harnesses/zeroboot.md)
* **`#code-mode`** (1): [Monty](02_agent_runtimes_and_harnesses/monty.md)
* **`#code-review`** (1): [Open Code Review](02_agent_runtimes_and_harnesses/open-code-review.md)
* **`#code-search`** (1): [zvec-grep (zg)](02_agent_runtimes_and_harnesses/zvec-grep.md)
* **`#codex`** (3): [Awesome DESIGN.md](02_agent_runtimes_and_harnesses/awesome-design-md.md), [Diagram Design](02_agent_runtimes_and_harnesses/diagram-design.md), [i-have-adhd](02_agent_runtimes_and_harnesses/i-have-adhd.md)
* **`#codex-cli`** (1): [GPT-5.6 Instruct](05_security_osint_and_guardrails/gpt-5.6-instruct.md)
* **`#coding-agents`** (1): [AI Agent Book](02_agent_runtimes_and_harnesses/ai-agent-book.md)
* **`#computer-use`** (1): [AIHawk](06_developer_tools_and_apps/ai-hawk.md)
* **`#container-security`** (1): [Анатомия ядра Linux и харденинг контейнеров](05_security_osint_and_guardrails/linux-kernel-and-container-hardening.md)
* **`#containers`** (1): [ArcBox](02_agent_runtimes_and_harnesses/arcbox.md)
* **`#context-compression`** (1): [SoL-Pi](02_agent_runtimes_and_harnesses/sol-pi.md)
* **`#context-engineering`** (1): [AI Agent Book](02_agent_runtimes_and_harnesses/ai-agent-book.md)
* **`#continuous-evolution`** (1): [AI Agent Book](02_agent_runtimes_and_harnesses/ai-agent-book.md)
* **`#copy-on-write`** (1): [ZeroBoot](02_agent_runtimes_and_harnesses/zeroboot.md)
* **`#crawl4ai`** (1): [Crawl4AI](06_developer_tools_and_apps/crawl4ai.md)
* **`#credential-offloading`** (1): [Архитектура Tool Broker & Execution Blocker](02_agent_runtimes_and_harnesses/tool-broker-architecture.md)
* **`#cursor`** (4): [Agent-Skills](02_agent_runtimes_and_harnesses/agent-skills.md), [Awesome DESIGN.md](02_agent_runtimes_and_harnesses/awesome-design-md.md), [i-have-adhd](02_agent_runtimes_and_harnesses/i-have-adhd.md), [Tencent BrowserSkill](06_developer_tools_and_apps/browserskill.md)
* **`#dast`** (1): [Ghost Security](05_security_osint_and_guardrails/ghost-security.md)
* **`#data-visualization`** (1): [Diagram Design](02_agent_runtimes_and_harnesses/diagram-design.md)
* **`#databases`** (1): [System Design 101](06_developer_tools_and_apps/system-design-101.md)
* **`#datalog`** (1): [Semantica AGI](03_knowledge_graphs_and_ontologies/semantica.md)
* **`#decision-intelligence`** (1): [Semantica AGI](03_knowledge_graphs_and_ontologies/semantica.md)
* **`#deep-learning`** (2): [LLMs from Scratch (Себастьян Рашка)](01_llm_architecture_and_training/LLMs-from-scratch.md), [Dive into LLMs (动手学大模型)](01_llm_architecture_and_training/dive-into-llms.md)
* **`#deep-research`** (1): [Hyperresearch](04_scientific_research_and_discovery/hyperresearch.md)
* **`#deepseek-r1`** (1): [Reasoning from Scratch (Себастьян Рашка](01_llm_architecture_and_training/reasoning-from-scratch.md)
* **`#design-systems`** (1): [Awesome DESIGN.md](02_agent_runtimes_and_harnesses/awesome-design-md.md)
* **`#desktop-app`** (1): [Fastpotify](06_developer_tools_and_apps/fastpotify.md)
* **`#deterministic-engineering`** (1): [Open Code Review](02_agent_runtimes_and_harnesses/open-code-review.md)
* **`#diagrams`** (1): [Diagram Design](02_agent_runtimes_and_harnesses/diagram-design.md)
* **`#digital-footprint`** (1): [User Scanner](05_security_osint_and_guardrails/user-scanner.md)
* **`#distributed-inference`** (1): [AI Infra Book](01_llm_architecture_and_training/ai-infra-book.md)
* **`#distributed-systems`** (1): [System Design 101](06_developer_tools_and_apps/system-design-101.md)
* **`#distributed-training`** (1): [AI Infra Book](01_llm_architecture_and_training/ai-infra-book.md)
* **`#dns-rebinding`** (1): [Smokescreen](05_security_osint_and_guardrails/smokescreen.md)
* **`#docker`** (2): [Dormice](02_agent_runtimes_and_harnesses/dormice.md), [Crawl4AI](06_developer_tools_and_apps/crawl4ai.md)
* **`#dpo`** (2): [Dive into LLMs (动手学大模型)](01_llm_architecture_and_training/dive-into-llms.md), [MiniMind](01_llm_architecture_and_training/minimind.md)
* **`#drug-discovery`** (1): [Scientific Agent Skills (K-Dense AI](04_scientific_research_and_discovery/scientific-agent-skills.md)
* **`#e2b-compatible`** (1): [Dormice](02_agent_runtimes_and_harnesses/dormice.md)
* **`#edr-evasion`** (1): [Claude-Red](05_security_osint_and_guardrails/claude-red.md)
* **`#education`** (2): [LLMs from Scratch (Себастьян Рашка)](01_llm_architecture_and_training/LLMs-from-scratch.md), [OpenMAIC](02_agent_runtimes_and_harnesses/openmaic.md)
* **`#efficiency`** (1): [SoL-Pi](02_agent_runtimes_and_harnesses/sol-pi.md)
* **`#egress-control`** (1): [Pipelock](05_security_osint_and_guardrails/pipelock.md)
* **`#egress-proxy`** (1): [Smokescreen](05_security_osint_and_guardrails/smokescreen.md)
* **`#egui`** (1): [Fastpotify](06_developer_tools_and_apps/fastpotify.md)
* **`#email-recon`** (1): [User Scanner](05_security_osint_and_guardrails/user-scanner.md)
* **`#evidence-ledger`** (1): [PRAXIST](04_scientific_research_and_discovery/praxist.md)
* **`#evolutionary-search`** (1): [PRAXIST](04_scientific_research_and_discovery/praxist.md)
* **`#exploit-development`** (1): [Claude-Red](05_security_osint_and_guardrails/claude-red.md)
* **`#fail-closed`** (1): [TCB & Reference Monitor](05_security_osint_and_guardrails/tcb-agent-security.md)
* **`#fallback-routing`** (1): [Agent-Reach](02_agent_runtimes_and_harnesses/agent-reach.md)
* **`#fine-tuning`** (1): [LLM-Master](01_llm_architecture_and_training/llm-master.md)
* **`#formatting`** (1): [i-have-adhd](02_agent_runtimes_and_harnesses/i-have-adhd.md)
* **`#from-scratch`** (1): [LLMs from Scratch (Себастьян Рашка)](01_llm_architecture_and_training/LLMs-from-scratch.md)
* **`#frontend`** (1): [Awesome DESIGN.md](02_agent_runtimes_and_harnesses/awesome-design-md.md)
* **`#fuzzing`** (1): [HuntProxy](05_security_osint_and_guardrails/huntproxy.md)
* **`#ghost-security`** (1): [Ghost Security](05_security_osint_and_guardrails/ghost-security.md)
* **`#git-diff`** (1): [Open Code Review](02_agent_runtimes_and_harnesses/open-code-review.md)
* **`#github`** (1): [Agent-Reach](02_agent_runtimes_and_harnesses/agent-reach.md)
* **`#go`** (4): [Open Code Review](02_agent_runtimes_and_harnesses/open-code-review.md), [Ghost Security](05_security_osint_and_guardrails/ghost-security.md), [Pipelock](05_security_osint_and_guardrails/pipelock.md), [Smokescreen](05_security_osint_and_guardrails/smokescreen.md)
* **`#grpo`** (2): [AI Engineering from Scratch (Рохит Гумаре](01_llm_architecture_and_training/ai-engineering-from-scratch.md), [Reasoning from Scratch (Себастьян Рашка](01_llm_architecture_and_training/reasoning-from-scratch.md)
* **`#guardrails`** (2): [CL4R1T4S](05_security_osint_and_guardrails/CL4R1T4S.md), [GPT-5.6 Instruct](05_security_osint_and_guardrails/gpt-5.6-instruct.md)
* **`#gvisor`** (1): [Dormice](02_agent_runtimes_and_harnesses/dormice.md)
* **`#hardware-constraints`** (1): [AI Infra Book](01_llm_architecture_and_training/ai-infra-book.md)
* **`#harness-engineering`** (2): [AI Agent Book](02_agent_runtimes_and_harnesses/ai-agent-book.md), [Learn Harness Engineering (Курс WalkingLabs](02_agent_runtimes_and_harnesses/learn-harness-engineering.md)
* **`#headless-browser`** (2): [HuntProxy](05_security_osint_and_guardrails/huntproxy.md), [Obscura](06_developer_tools_and_apps/obscura.md)
* **`#high-performance`** (1): [ZeroBoot](02_agent_runtimes_and_harnesses/zeroboot.md)
* **`#html`** (1): [Diagram Design](02_agent_runtimes_and_harnesses/diagram-design.md)
* **`#human-in-the-loop`** (1): [Tencent BrowserSkill](06_developer_tools_and_apps/browserskill.md)
* **`#huntproxy`** (1): [HuntProxy](05_security_osint_and_guardrails/huntproxy.md)
* **`#hybrid-search`** (1): [zvec-grep (zg)](02_agent_runtimes_and_harnesses/zvec-grep.md)
* **`#idle-zero-cost`** (1): [Dormice](02_agent_runtimes_and_harnesses/dormice.md)
* **`#inference-scaling`** (1): [Reasoning from Scratch (Себастьян Рашка](01_llm_architecture_and_training/reasoning-from-scratch.md)
* **`#interactive-learning`** (1): [OpenMAIC](02_agent_runtimes_and_harnesses/openmaic.md)
* **`#interview-prep`** (1): [LLM-Master](01_llm_architecture_and_training/llm-master.md)
* **`#jailbreak-analysis`** (1): [CL4R1T4S](05_security_osint_and_guardrails/CL4R1T4S.md)
* **`#jailbreak-testing`** (1): [GPT-5.6 Instruct](05_security_osint_and_guardrails/gpt-5.6-instruct.md)
* **`#json-findings`** (1): [Cloudflare Security Audit Skill](05_security_osint_and_guardrails/security-audit-skill.md)
* **`#jupyter`** (1): [Dive into LLMs (动手学大模型)](01_llm_architecture_and_training/dive-into-llms.md)
* **`#kernel-hardening`** (1): [Анатомия ядра Linux и харденинг контейнеров](05_security_osint_and_guardrails/linux-kernel-and-container-hardening.md)
* **`#knowledge-graphs`** (2): [Semantica AGI](03_knowledge_graphs_and_ontologies/semantica.md), [Utopia](03_knowledge_graphs_and_ontologies/utopia.md)
* **`#knowledge-vault`** (1): [Hyperresearch](04_scientific_research_and_discovery/hyperresearch.md)
* **`#kv-cache`** (2): [AI Infra Book](01_llm_architecture_and_training/ai-infra-book.md), [AI Agent Book](02_agent_runtimes_and_harnesses/ai-agent-book.md)
* **`#latex`** (1): [Academic Research Skills](04_scientific_research_and_discovery/academic-research-skills.md)
* **`#learning-roadmap`** (1): [Capstone Roadmap](00_strategy_and_roadmaps/capstone-engineering-roadmap.md)
* **`#lethal-trifecta`** (1): [Архитектура Tool Broker & Execution Blocker](02_agent_runtimes_and_harnesses/tool-broker-architecture.md)
* **`#librespot`** (1): [Fastpotify](06_developer_tools_and_apps/fastpotify.md)
* **`#lightweight-models`** (1): [MiniMind](01_llm_architecture_and_training/minimind.md)
* **`#line-level-precision`** (1): [Open Code Review](02_agent_runtimes_and_harnesses/open-code-review.md)
* **`#linux-insides`** (1): [Анатомия ядра Linux и харденинг контейнеров](05_security_osint_and_guardrails/linux-kernel-and-container-hardening.md)
* **`#linux-kernel`** (1): [Анатомия ядра Linux и харденинг контейнеров](05_security_osint_and_guardrails/linux-kernel-and-container-hardening.md)
* **`#llm`** (3): [LLMs from Scratch (Себастьян Рашка)](01_llm_architecture_and_training/LLMs-from-scratch.md), [Dive into LLMs (动手学大模型)](01_llm_architecture_and_training/dive-into-llms.md), [MiniMind](01_llm_architecture_and_training/minimind.md)
* **`#llm-master`** (1): [LLM-Master](01_llm_architecture_and_training/llm-master.md)
* **`#llm-ready`** (1): [Crawl4AI](06_developer_tools_and_apps/crawl4ai.md)
* **`#llm-roadmap`** (1): [LLM-Master](01_llm_architecture_and_training/llm-master.md)
* **`#llm-security`** (1): [API Relay Audit](05_security_osint_and_guardrails/api-relay-audit.md)
* **`#local-first`** (2): [zvec-grep (zg)](02_agent_runtimes_and_harnesses/zvec-grep.md), [Utopia](03_knowledge_graphs_and_ontologies/utopia.md)
* **`#loop-breaker`** (1): [Архитектура Tool Broker & Execution Blocker](02_agent_runtimes_and_harnesses/tool-broker-architecture.md)
* **`#lora`** (2): [Dive into LLMs (动手学大模型)](01_llm_architecture_and_training/dive-into-llms.md), [MiniMind](01_llm_architecture_and_training/minimind.md)
* **`#markdown`** (1): [Crawl4AI](06_developer_tools_and_apps/crawl4ai.md)
* **`#material-design`** (1): [M3E Canvas](02_agent_runtimes_and_harnesses/m3e-canvas.md)
* **`#mcp`** (12): [AI Engineering from Scratch (Рохит Гумаре](01_llm_architecture_and_training/ai-engineering-from-scratch.md), [LLM-Master](01_llm_architecture_and_training/llm-master.md), [Agent-Reach](02_agent_runtimes_and_harnesses/agent-reach.md), [Agent-Skills](02_agent_runtimes_and_harnesses/agent-skills.md), [AI Agent Book](02_agent_runtimes_and_harnesses/ai-agent-book.md), [Learn Harness Engineering (Курс WalkingLabs](02_agent_runtimes_and_harnesses/learn-harness-engineering.md), [Utopia](03_knowledge_graphs_and_ontologies/utopia.md), [Hyperresearch](04_scientific_research_and_discovery/hyperresearch.md), [Ghost Security](05_security_osint_and_guardrails/ghost-security.md), [HuntProxy](05_security_osint_and_guardrails/huntproxy.md), [SkillSpector](05_security_osint_and_guardrails/skillspector.md), [AIHawk](06_developer_tools_and_apps/ai-hawk.md)
* **`#mcp-router`** (1): [Архитектура Tool Broker & Execution Blocker](02_agent_runtimes_and_harnesses/tool-broker-architecture.md)
* **`#mcp-security`** (1): [Pipelock](05_security_osint_and_guardrails/pipelock.md)
* **`#mediator-receipts`** (1): [Pipelock](05_security_osint_and_guardrails/pipelock.md)
* **`#micro-runtime`** (1): [Monty](02_agent_runtimes_and_harnesses/monty.md)
* **`#micro-vm`** (2): [ArcBox](02_agent_runtimes_and_harnesses/arcbox.md), [ZeroBoot](02_agent_runtimes_and_harnesses/zeroboot.md)
* **`#microservices`** (1): [System Design 101](06_developer_tools_and_apps/system-design-101.md)
* **`#mitm-proxy`** (1): [Ghost Security](05_security_osint_and_guardrails/ghost-security.md)
* **`#model-substitution`** (1): [API Relay Audit](05_security_osint_and_guardrails/api-relay-audit.md)
* **`#multi-agent`** (2): [AI Agent Book](02_agent_runtimes_and_harnesses/ai-agent-book.md), [OpenMAIC](02_agent_runtimes_and_harnesses/openmaic.md)
* **`#multi-platform`** (1): [Agent-Reach](02_agent_runtimes_and_harnesses/agent-reach.md)
* **`#namespaces`** (1): [Анатомия ядра Linux и харденинг контейнеров](05_security_osint_and_guardrails/linux-kernel-and-container-hardening.md)
* **`#ncc-group`** (1): [Анатомия ядра Linux и харденинг контейнеров](05_security_osint_and_guardrails/linux-kernel-and-container-hardening.md)
* **`#network-security`** (1): [Smokescreen](05_security_osint_and_guardrails/smokescreen.md)
* **`#no-mermaid`** (1): [Diagram Design](02_agent_runtimes_and_harnesses/diagram-design.md)
* **`#nvidia`** (2): [SoL-Pi](02_agent_runtimes_and_harnesses/sol-pi.md), [SkillSpector](05_security_osint_and_guardrails/skillspector.md)
* **`#observation-pack`** (1): [SoL-Pi](02_agent_runtimes_and_harnesses/sol-pi.md)
* **`#oci`** (1): [ArcBox](02_agent_runtimes_and_harnesses/arcbox.md)
* **`#offensive-security`** (1): [Claude-Red](05_security_osint_and_guardrails/claude-red.md)
* **`#ontologies`** (1): [Utopia](03_knowledge_graphs_and_ontologies/utopia.md)
* **`#open-code-review`** (1): [Open Code Review](02_agent_runtimes_and_harnesses/open-code-review.md)
* **`#open-source-book`** (2): [AI Infra Book](01_llm_architecture_and_training/ai-infra-book.md), [AI Agent Book](02_agent_runtimes_and_harnesses/ai-agent-book.md)
* **`#osint`** (1): [User Scanner](05_security_osint_and_guardrails/user-scanner.md)
* **`#peer-review`** (2): [Academic Research Skills](04_scientific_research_and_discovery/academic-research-skills.md), [Hyperresearch](04_scientific_research_and_discovery/hyperresearch.md)
* **`#pen-testing`** (1): [Claude-Red](05_security_osint_and_guardrails/claude-red.md)
* **`#pi-agent`** (1): [SoL-Pi](02_agent_runtimes_and_harnesses/sol-pi.md)
* **`#playwright`** (2): [AIHawk](06_developer_tools_and_apps/ai-hawk.md), [Crawl4AI](06_developer_tools_and_apps/crawl4ai.md)
* **`#post-training`** (1): [AI Agent Book](02_agent_runtimes_and_harnesses/ai-agent-book.md)
* **`#pretraining`** (2): [Dive into LLMs (动手学大模型)](01_llm_architecture_and_training/dive-into-llms.md), [MiniMind](01_llm_architecture_and_training/minimind.md)
* **`#productivity`** (1): [i-have-adhd](02_agent_runtimes_and_harnesses/i-have-adhd.md)
* **`#programmatic-tool-calling`** (1): [Monty](02_agent_runtimes_and_harnesses/monty.md)
* **`#prompt-engineering`** (6): [LLM-Master](01_llm_architecture_and_training/llm-master.md), [Awesome DESIGN.md](02_agent_runtimes_and_harnesses/awesome-design-md.md), [i-have-adhd](02_agent_runtimes_and_harnesses/i-have-adhd.md), [M3E Canvas](02_agent_runtimes_and_harnesses/m3e-canvas.md), [CL4R1T4S](05_security_osint_and_guardrails/CL4R1T4S.md), [Claude-Red](05_security_osint_and_guardrails/claude-red.md)
* **`#prompt-injection`** (5): [API Relay Audit](05_security_osint_and_guardrails/api-relay-audit.md), [Pipelock](05_security_osint_and_guardrails/pipelock.md), [Cloudflare Security Audit Skill](05_security_osint_and_guardrails/security-audit-skill.md), [SkillSpector](05_security_osint_and_guardrails/skillspector.md), [TCB & Reference Monitor](05_security_osint_and_guardrails/tcb-agent-security.md)
* **`#prototyping`** (1): [M3E Canvas](02_agent_runtimes_and_harnesses/m3e-canvas.md)
* **`#prov-o`** (1): [Semantica AGI](03_knowledge_graphs_and_ontologies/semantica.md)
* **`#pubmed`** (1): [Scientific Agent Skills (K-Dense AI](04_scientific_research_and_discovery/scientific-agent-skills.md)
* **`#pydantic`** (1): [Monty](02_agent_runtimes_and_harnesses/monty.md)
* **`#python`** (2): [User Scanner](05_security_osint_and_guardrails/user-scanner.md), [AIHawk](06_developer_tools_and_apps/ai-hawk.md)
* **`#python-interpreter`** (1): [Monty](02_agent_runtimes_and_harnesses/monty.md)
* **`#pytorch`** (2): [LLMs from Scratch (Себастьян Рашка)](01_llm_architecture_and_training/LLMs-from-scratch.md), [MiniMind](01_llm_architecture_and_training/minimind.md)
* **`#quantization`** (1): [Dive into LLMs (动手学大模型)](01_llm_architecture_and_training/dive-into-llms.md)
* **`#r-and-d`** (1): [PRAXIST](04_scientific_research_and_discovery/praxist.md)
* **`#rag`** (3): [AI Engineering from Scratch (Рохит Гумаре](01_llm_architecture_and_training/ai-engineering-from-scratch.md), [LLM-Master](01_llm_architecture_and_training/llm-master.md), [Crawl4AI](06_developer_tools_and_apps/crawl4ai.md)
* **`#rdma`** (1): [AI Infra Book](01_llm_architecture_and_training/ai-infra-book.md)
* **`#react`** (1): [M3E Canvas](02_agent_runtimes_and_harnesses/m3e-canvas.md)
* **`#reaper`** (1): [Ghost Security](05_security_osint_and_guardrails/ghost-security.md)
* **`#reasoning`** (1): [Reasoning from Scratch (Себастьян Рашка](01_llm_architecture_and_training/reasoning-from-scratch.md)
* **`#red-teaming`** (3): [CL4R1T4S](05_security_osint_and_guardrails/CL4R1T4S.md), [Claude-Red](05_security_osint_and_guardrails/claude-red.md), [GPT-5.6 Instruct](05_security_osint_and_guardrails/gpt-5.6-instruct.md)
* **`#reddit`** (1): [Agent-Reach](02_agent_runtimes_and_harnesses/agent-reach.md)
* **`#reference-monitor`** (1): [TCB & Reference Monitor](05_security_osint_and_guardrails/tcb-agent-security.md)
* **`#reinforcement-learning`** (1): [Reasoning from Scratch (Себастьян Рашка](01_llm_architecture_and_training/reasoning-from-scratch.md)
* **`#rete`** (1): [Semantica AGI](03_knowledge_graphs_and_ontologies/semantica.md)
* **`#rlhf`** (1): [Dive into LLMs (动手学大模型)](01_llm_architecture_and_training/dive-into-llms.md)
* **`#rlvr`** (1): [Reasoning from Scratch (Себастьян Рашка](01_llm_architecture_and_training/reasoning-from-scratch.md)
* **`#roadmap`** (1): [AI Engineering from Scratch (Рохит Гумаре](01_llm_architecture_and_training/ai-engineering-from-scratch.md)
* **`#roofline-model`** (1): [AI Infra Book](01_llm_architecture_and_training/ai-infra-book.md)
* **`#rust`** (9): [ArcBox](02_agent_runtimes_and_harnesses/arcbox.md), [Atlas](02_agent_runtimes_and_harnesses/atlas.md), [Monty](02_agent_runtimes_and_harnesses/monty.md), [ZeroBoot](02_agent_runtimes_and_harnesses/zeroboot.md), [Utopia](03_knowledge_graphs_and_ontologies/utopia.md), [HuntProxy](05_security_osint_and_guardrails/huntproxy.md), [Tencent BrowserSkill](06_developer_tools_and_apps/browserskill.md), [Fastpotify](06_developer_tools_and_apps/fastpotify.md), [Obscura](06_developer_tools_and_apps/obscura.md)
* **`#sandboxing`** (4): [ArcBox](02_agent_runtimes_and_harnesses/arcbox.md), [Анатомия ядра Linux и харденинг контейнеров](05_security_osint_and_guardrails/linux-kernel-and-container-hardening.md), [Cloudflare Security Audit Skill](05_security_osint_and_guardrails/security-audit-skill.md), [TCB & Reference Monitor](05_security_osint_and_guardrails/tcb-agent-security.md)
* **`#sarif`** (1): [Cloudflare Security Audit Skill](05_security_osint_and_guardrails/security-audit-skill.md)
* **`#sast`** (1): [Ghost Security](05_security_osint_and_guardrails/ghost-security.md)
* **`#sca`** (1): [Ghost Security](05_security_osint_and_guardrails/ghost-security.md)
* **`#scientific-writing`** (1): [Academic Research Skills](04_scientific_research_and_discovery/academic-research-skills.md)
* **`#search`** (1): [zvec-grep (zg)](02_agent_runtimes_and_harnesses/zvec-grep.md)
* **`#seccomp-bpf`** (1): [Анатомия ядра Linux и харденинг контейнеров](05_security_osint_and_guardrails/linux-kernel-and-container-hardening.md)
* **`#secret-broker`** (1): [TCB & Reference Monitor](05_security_osint_and_guardrails/tcb-agent-security.md)
* **`#security`** (4): [Monty](02_agent_runtimes_and_harnesses/monty.md), [Архитектура Tool Broker & Execution Blocker](02_agent_runtimes_and_harnesses/tool-broker-architecture.md), [GPT-5.6 Instruct](05_security_osint_and_guardrails/gpt-5.6-instruct.md), [User Scanner](05_security_osint_and_guardrails/user-scanner.md)
* **`#security-audit`** (2): [Ghost Security](05_security_osint_and_guardrails/ghost-security.md), [Cloudflare Security Audit Skill](05_security_osint_and_guardrails/security-audit-skill.md)
* **`#security-audit-skill`** (1): [Cloudflare Security Audit Skill](05_security_osint_and_guardrails/security-audit-skill.md)
* **`#security-rules`** (1): [Open Code Review](02_agent_runtimes_and_harnesses/open-code-review.md)
* **`#security-workbench`** (1): [HuntProxy](05_security_osint_and_guardrails/huntproxy.md)
* **`#self-hosted`** (1): [Dormice](02_agent_runtimes_and_harnesses/dormice.md)
* **`#selinux`** (1): [Анатомия ядра Linux и харденинг контейнеров](05_security_osint_and_guardrails/linux-kernel-and-container-hardening.md)
* **`#semantic-search`** (1): [zvec-grep (zg)](02_agent_runtimes_and_harnesses/zvec-grep.md)
* **`#sft`** (2): [Dive into LLMs (动手学大模型)](01_llm_architecture_and_training/dive-into-llms.md), [MiniMind](01_llm_architecture_and_training/minimind.md)
* **`#shacl`** (1): [Semantica AGI](03_knowledge_graphs_and_ontologies/semantica.md)
* **`#sitemap-discovery`** (1): [HuntProxy](05_security_osint_and_guardrails/huntproxy.md)
* **`#skill-md`** (1): [Claude-Red](05_security_osint_and_guardrails/claude-red.md)
* **`#skill-registry`** (1): [Agent-Skills](02_agent_runtimes_and_harnesses/agent-skills.md)
* **`#skill-scanner`** (1): [SkillSpector](05_security_osint_and_guardrails/skillspector.md)
* **`#snyk-agent-scan`** (1): [Agent-Skills](02_agent_runtimes_and_harnesses/agent-skills.md)
* **`#socratic-planning`** (1): [Academic Research Skills](04_scientific_research_and_discovery/academic-research-skills.md)
* **`#source-control`** (1): [Atlas](02_agent_runtimes_and_harnesses/atlas.md)
* **`#spec-driven`** (1): [Agent-Skills](02_agent_runtimes_and_harnesses/agent-skills.md)
* **`#spotify`** (1): [Fastpotify](06_developer_tools_and_apps/fastpotify.md)
* **`#sse-anomalies`** (1): [API Relay Audit](05_security_osint_and_guardrails/api-relay-audit.md)
* **`#ssrf-prevention`** (3): [Pipelock](05_security_osint_and_guardrails/pipelock.md), [Smokescreen](05_security_osint_and_guardrails/smokescreen.md), [TCB & Reference Monitor](05_security_osint_and_guardrails/tcb-agent-security.md)
* **`#static-analysis`** (1): [SkillSpector](05_security_osint_and_guardrails/skillspector.md)
* **`#stealth-browser`** (1): [AIHawk](06_developer_tools_and_apps/ai-hawk.md)
* **`#strategy`** (1): [Capstone Roadmap](00_strategy_and_roadmaps/capstone-engineering-roadmap.md)
* **`#stripe`** (1): [Smokescreen](05_security_osint_and_guardrails/smokescreen.md)
* **`#structured-extraction`** (1): [Crawl4AI](06_developer_tools_and_apps/crawl4ai.md)
* **`#supply-chain`** (1): [SkillSpector](05_security_osint_and_guardrails/skillspector.md)
* **`#supply-chain-security`** (1): [Agent-Skills](02_agent_runtimes_and_harnesses/agent-skills.md)
* **`#svg`** (1): [Diagram Design](02_agent_runtimes_and_harnesses/diagram-design.md)
* **`#system-architecture`** (1): [Capstone Roadmap](00_strategy_and_roadmaps/capstone-engineering-roadmap.md)
* **`#system-design`** (3): [AI Infra Book](01_llm_architecture_and_training/ai-infra-book.md), [LLM-Master](01_llm_architecture_and_training/llm-master.md), [System Design 101](06_developer_tools_and_apps/system-design-101.md)
* **`#system-prompts`** (1): [CL4R1T4S](05_security_osint_and_guardrails/CL4R1T4S.md)
* **`#tab-borrowing`** (1): [Tencent BrowserSkill](06_developer_tools_and_apps/browserskill.md)
* **`#tcb`** (3): [Pipelock](05_security_osint_and_guardrails/pipelock.md), [Smokescreen](05_security_osint_and_guardrails/smokescreen.md), [TCB & Reference Monitor](05_security_osint_and_guardrails/tcb-agent-security.md)
* **`#tencent`** (1): [Tencent BrowserSkill](06_developer_tools_and_apps/browserskill.md)
* **`#token-diet`** (1): [SoL-Pi](02_agent_runtimes_and_harnesses/sol-pi.md)
* **`#token-efficiency`** (1): [Open Code Review](02_agent_runtimes_and_harnesses/open-code-review.md)
* **`#tool-broker`** (1): [Архитектура Tool Broker & Execution Blocker](02_agent_runtimes_and_harnesses/tool-broker-architecture.md)
* **`#tool-call-tampering`** (1): [API Relay Audit](05_security_osint_and_guardrails/api-relay-audit.md)
* **`#tool-gateway`** (1): [Архитектура Tool Broker & Execution Blocker](02_agent_runtimes_and_harnesses/tool-broker-architecture.md)
* **`#tool-rag`** (1): [Архитектура Tool Broker & Execution Blocker](02_agent_runtimes_and_harnesses/tool-broker-architecture.md)
* **`#transformers`** (3): [LLMs from Scratch (Себастьян Рашка)](01_llm_architecture_and_training/LLMs-from-scratch.md), [Dive into LLMs (动手学大模型)](01_llm_architecture_and_training/dive-into-llms.md), [LLM-Master](01_llm_architecture_and_training/llm-master.md)
* **`#transparency`** (1): [CL4R1T4S](05_security_osint_and_guardrails/CL4R1T4S.md)
* **`#tree-sitter`** (1): [Atlas](02_agent_runtimes_and_harnesses/atlas.md)
* **`#trusted-computing-base`** (1): [TCB & Reference Monitor](05_security_osint_and_guardrails/tcb-agent-security.md)
* **`#twitter`** (1): [Agent-Reach](02_agent_runtimes_and_harnesses/agent-reach.md)
* **`#typescript`** (3): [Agent-Skills](02_agent_runtimes_and_harnesses/agent-skills.md), [Dormice](02_agent_runtimes_and_harnesses/dormice.md), [OpenMAIC](02_agent_runtimes_and_harnesses/openmaic.md)
* **`#ui-ux`** (2): [Awesome DESIGN.md](02_agent_runtimes_and_harnesses/awesome-design-md.md), [M3E Canvas](02_agent_runtimes_and_harnesses/m3e-canvas.md)
* **`#username-scanner`** (1): [User Scanner](05_security_osint_and_guardrails/user-scanner.md)
* **`#ux`** (1): [i-have-adhd](02_agent_runtimes_and_harnesses/i-have-adhd.md)
* **`#vcs`** (1): [Atlas](02_agent_runtimes_and_harnesses/atlas.md)
* **`#vector-search`** (1): [zvec-grep (zg)](02_agent_runtimes_and_harnesses/zvec-grep.md)
* **`#verified-skills`** (1): [Agent-Skills](02_agent_runtimes_and_harnesses/agent-skills.md)
* **`#vibe-coding`** (1): [M3E Canvas](02_agent_runtimes_and_harnesses/m3e-canvas.md)
* **`#virtualization`** (1): [ZeroBoot](02_agent_runtimes_and_harnesses/zeroboot.md)
* **`#visual-guide`** (1): [System Design 101](06_developer_tools_and_apps/system-design-101.md)
* **`#vllm`** (4): [AI Engineering from Scratch (Рохит Гумаре](01_llm_architecture_and_training/ai-engineering-from-scratch.md), [AI Infra Book](01_llm_architecture_and_training/ai-infra-book.md), [Dive into LLMs (动手学大模型)](01_llm_architecture_and_training/dive-into-llms.md), [LLM-Master](01_llm_architecture_and_training/llm-master.md)
* **`#vulnerability-assessment`** (1): [Cloudflare Security Audit Skill](05_security_osint_and_guardrails/security-audit-skill.md)
* **`#vulnerability-research`** (1): [Claude-Red](05_security_osint_and_guardrails/claude-red.md)
* **`#web-automation`** (1): [AIHawk](06_developer_tools_and_apps/ai-hawk.md)
* **`#web-crawler`** (1): [Crawl4AI](06_developer_tools_and_apps/crawl4ai.md)
* **`#web-scraping`** (4): [Agent-Reach](02_agent_runtimes_and_harnesses/agent-reach.md), [Hyperresearch](04_scientific_research_and_discovery/hyperresearch.md), [Crawl4AI](06_developer_tools_and_apps/crawl4ai.md), [Obscura](06_developer_tools_and_apps/obscura.md)
* **`#web-security`** (1): [HuntProxy](05_security_osint_and_guardrails/huntproxy.md)
* **`#webrtc`** (1): [OpenMAIC](02_agent_runtimes_and_harnesses/openmaic.md)
* **`#world-model`** (1): [Utopia](03_knowledge_graphs_and_ontologies/utopia.md)
* **`#youtube`** (1): [Agent-Reach](02_agent_runtimes_and_harnesses/agent-reach.md)
* **`#zero-api-fees`** (1): [Agent-Reach](02_agent_runtimes_and_harnesses/agent-reach.md)
* **`#zero-trust`** (1): [TCB & Reference Monitor](05_security_osint_and_guardrails/tcb-agent-security.md)

---
*Сгенерировано автоматически: 2026-09-14 | Antigravity Knowledge Base*