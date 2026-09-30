# Awesome Prompt Engineering 🧠✨

[![ci](https://github.com/dakotac1994/awesome-prompt-engineering/actions/workflows/ci.yml/badge.svg)](https://github.com/dakotac1994/awesome-prompt-engineering/actions/workflows/ci.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

A curated, research-backed guide to **prompt engineering**: prompting techniques, frameworks & libraries, tooling, evaluation & optimization methods, guides, key papers, and prompt security.

> **Verification policy:** every entry links to its official source (paper, repo, or docs). An entry marked ✅ was checked against that source on the listed date; anything we couldn't confirm is marked ⚠️ unverified instead of guessed. See [`data/prompt-engineering.json`](data/prompt-engineering.json) for the machine-readable list with verification metadata.

## Contents

- [Prompting techniques](#prompting-techniques) (24)
- [Frameworks & libraries](#frameworks--libraries) (13)
- [Tooling & platforms](#tooling--platforms) (9)
- [Evaluation & optimization](#evaluation--optimization) (14)
- [Guides & playbooks](#guides--playbooks) (10)
- [Papers & surveys](#papers--surveys) (7)
- [Prompt security](#prompt-security) (3)

- [Related](#related)
- [Contributing](#contributing)
- [License](#license)

## Prompting techniques

- [Few-Shot Prompting](https://arxiv.org/abs/2005.14165) — In-context learning: give the model a few input-output examples in the prompt; the technique introduced alongside GPT-3 (Brown et al., 2020). ✅ verified 2026-09-30
- [Chain-of-Thought Prompting](https://arxiv.org/abs/2201.11903) — Elicit step-by-step reasoning with intermediate rationales; large gains on arithmetic and symbolic tasks (Wei et al., 2022). ✅ verified 2026-09-30
- [Zero-Shot Chain-of-Thought](https://arxiv.org/abs/2205.11916) — Append 'Let's think step by step' to trigger reasoning with no examples (Kojima et al., 2022). ✅ verified 2026-09-30
- [Self-Consistency](https://arxiv.org/abs/2203.11171) — Sample multiple reasoning paths and take the majority answer; improves over greedy CoT decoding (Wang et al., 2022). ✅ verified 2026-09-30
- [Least-to-Most Prompting](https://arxiv.org/abs/2205.10625) — Decompose a problem into easier subproblems and solve them sequentially (Zhou et al., 2022). ✅ verified 2026-09-30
- [Generated Knowledge Prompting](https://arxiv.org/abs/2110.08387) — First generate relevant knowledge statements, then condition the answer on them; helps commonsense reasoning (Liu et al., 2022). ✅ verified 2026-09-30
- [Scratchpad](https://arxiv.org/abs/2112.00114) — Let the model write intermediate computation into a 'scratchpad' before answering (Nye et al., 2021). ✅ verified 2026-09-30
- [ReAct](https://arxiv.org/abs/2210.03629) — Interleave reasoning traces with actions (search, tools); synergizes chain-of-thought with tool use (Yao et al., 2022). ✅ verified 2026-09-30
- [Program-Aided Language Models (PAL)](https://arxiv.org/abs/2211.10435) — Offload computation to a Python interpreter: the model writes code, the runtime executes it (Gao et al., 2022). ✅ verified 2026-09-30
- [Plan-and-Solve Prompting](https://arxiv.org/abs/2305.04091) — First devise a plan dividing the task into subtasks, then execute it; strengthens zero-shot CoT (Wang et al., 2023). ✅ verified 2026-09-30
- [ART](https://arxiv.org/abs/2303.09014) — Automatic multi-step reasoning and tool use: pause generation at tool calls, resume with the outputs (Paranjape et al., 2023). ✅ verified 2026-09-30
- [ReWOO](https://arxiv.org/abs/2305.18323) — Decouple reasoning from observations: plan all tool calls upfront (planner/worker/solver), cutting token cost (Xu et al., 2023). ✅ verified 2026-09-30
- [Tree of Thoughts](https://arxiv.org/abs/2305.10601) — Search over coherent thought units with lookahead and backtracking for deliberate problem solving (Yao et al., 2023). ✅ verified 2026-09-30
- [Graph of Thoughts](https://arxiv.org/abs/2308.09687) — Generalize tree search to arbitrary graph topologies over thought units for elaborate problems (Besta et al., 2023). ✅ verified 2026-09-30
- [Self-Refine](https://arxiv.org/abs/2303.17651) — Iterative refinement loop: generate, self-critique with feedback, refine (Madaan et al., 2023). ✅ verified 2026-09-30
- [Reflexion](https://arxiv.org/abs/2303.11366) — Verbal reinforcement learning: agents reflect on failures in natural language and retry (Shinn et al., 2023). ✅ verified 2026-09-30
- [Active Prompting](https://arxiv.org/abs/2302.12246) — Select the most uncertain examples for human annotation to build better few-shot CoT sets (Diao et al., 2023). ✅ verified 2026-09-30
- [Complexity-Based Prompting](https://arxiv.org/abs/2210.00720) — Prefer few-shot examples with more reasoning steps; complex prompts transfer better (Fu et al., 2022). ✅ verified 2026-09-30
- [Contrastive Chain-of-Thought](https://arxiv.org/abs/2311.09277) — Show both valid and invalid reasoning demonstrations so the model learns what mistakes to avoid (Chia et al., 2023). ✅ verified 2026-09-30
- [Directional Stimulus Prompting](https://arxiv.org/abs/2302.11520) — A small tunable model generates hints ('stimuli') that steer a frozen LLM (Li et al., 2023). ✅ verified 2026-09-30
- [Analogical Prompting](https://arxiv.org/abs/2310.01714) — Ask the model to recall analogous problems and solve them first, then tackle the target (Yasunaga et al., 2023). ✅ verified 2026-09-30
- [Multi-Agent Debate](https://arxiv.org/abs/2305.14325) — Several model instances debate with self-generated arguments; improves factuality and reasoning (Du et al., 2023). ✅ verified 2026-09-30
- [Meta-Prompting](https://arxiv.org/abs/2401.12954) — One LM acts as conductor, delegating subtasks to tailored 'expert' instances of itself; zero-shot and task-agnostic (Suzgun & Kalai, 2024). ✅ verified 2026-09-30
- [Prompt Chaining](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview) — Split a task into sequential LLM steps where each step's output feeds the next; a core production pattern in the vendor guides. ✅ verified 2026-09-30
## Frameworks & libraries

- [DSPy](https://github.com/stanfordnlp/dspy) — Stanford framework for programming LMs: composable modules (signatures) plus optimizers instead of hand-written prompts. ✅ verified 2026-09-30
- [LangChain](https://github.com/langchain-ai/langchain) — Framework for LLM apps: prompt templates, chains, agents, and a large integration ecosystem. ✅ verified 2026-09-30
- [Guidance](https://github.com/guidance-ai/guidance) — Control language interleaving generation with programming logic: regex, CFGs, and structured control flow. ✅ verified 2026-09-30
- [LMQL](https://github.com/eth-sri/lmql) — Query language for LLMs with constraints, scripting, and decoding control (ETH SRI). ✅ verified 2026-09-30
- [Outlines](https://github.com/dottxt-ai/outlines) — Structured text generation: constrain decoding with regex, JSON schema, or grammars. ✅ verified 2026-09-30
- [Instructor](https://github.com/567-labs/instructor) — Structured LLM outputs in Python: Pydantic-validated responses with automatic retries. ✅ verified 2026-09-30
- [BAML](https://github.com/BoundaryML/baml) — Typed prompt functions: write prompts as functions with schemas; Boundary's LLM-function language. ✅ verified 2026-09-30
- [ell](https://github.com/MadcowD/ell) — Lightweight prompt-engineering library: prompts as versioned, testable Python functions. ✅ verified 2026-09-30
- [APPL](https://github.com/appl-team/appl) — Prompt programming language: embed natural-language prompts in Python with async parallelization and tracing. ✅ verified 2026-09-30
- [marvin](https://github.com/PrefectHQ/marvin) — Prefect's AI engineering framework: typed, testable LLM functions via Python decorators. ✅ verified 2026-09-30
- [Semantic Kernel](https://github.com/microsoft/semantic-kernel) — Microsoft's SDK for wiring LLMs into apps: semantic functions, planners, and plugins. ✅ verified 2026-09-30
- [Mirascope](https://github.com/Mirascope/mirascope) — Typed, provider-agnostic LLM calls in Python with prompt templates built from type hints. ✅ verified 2026-09-30
- [TypeChat](https://github.com/microsoft/TypeChat) — Microsoft's TypeScript library for building typed natural-language interfaces. ✅ verified 2026-09-30
## Tooling & platforms

- [Promptfoo](https://promptfoo.dev) — Open-source LLM eval toolkit: assertions, red-teaming, and CI-ready prompt test runs. ✅ verified 2026-09-30
- [LangSmith](https://www.langchain.com/langsmith) — LangChain's platform for prompt iteration: prompt hub/versioning, tracing, and evals. ✅ verified 2026-09-30
- [Langfuse](https://langfuse.com/docs) — Open-source LLM engineering platform: prompt management and versioning, tracing, analytics. ✅ verified 2026-09-30
- [Helicone](https://www.helicone.ai) — Open-source LLM observability proxy: request logging, caching, rate limits, and evals. ✅ verified 2026-09-30
- [W&B Weave](https://wandb.ai/site/weave) — Weights & Biases toolkit for tracing, versioning, and evaluating LLM calls. ✅ verified 2026-09-30
- [PromptLayer](https://www.promptlayer.com) — Prompt registry with versioning and release labels, request logging, and evals; Python/JS SDKs. ✅ verified 2026-09-30
- [Vellum](https://www.vellum.ai) — Prompt playground, versioning, and workflow builder for production LLM apps. ✅ verified 2026-09-30
- [OpenAI Playground](https://platform.openai.com/playground) — OpenAI's hosted console for iterating on prompts across models and parameters. ✅ verified 2026-09-30
- [Anthropic Workbench](https://console.anthropic.com/workbench) — Anthropic Console's prompt IDE: iterate, compare, and test prompts. ✅ verified 2026-09-30
## Evaluation & optimization

- [Automatic Prompt Engineer (APE)](https://arxiv.org/abs/2211.01910) — LLMs as human-level prompt engineers: generate and select instructions automatically (Zhou et al., 2022). ✅ verified 2026-09-30
- [OPRO](https://arxiv.org/abs/2309.03409) — Optimization by PROmpting: use an LLM as the optimizer, described in natural language (Yang et al., 2023). ✅ verified 2026-09-30
- [Promptbreeder](https://arxiv.org/abs/2309.16797) — Self-referential self-improvement: evolve both task-prompts and mutation-prompts (Fernando et al., 2023). ✅ verified 2026-09-30
- [EvoPrompt](https://arxiv.org/abs/2309.08532) — Connect LLMs with evolutionary algorithms for discrete prompt optimization (Guo et al., 2023). ✅ verified 2026-09-30
- [ProTeGi](https://arxiv.org/abs/2305.03495) — Automatic prompt optimization with textual 'gradient descent' and beam search (Pryzant et al., 2023). ✅ verified 2026-09-30
- [TextGrad](https://arxiv.org/abs/2406.07496) — Automatic 'differentiation' via text: backpropagate natural-language feedback through compound AI systems (Yuksekgonul et al., 2024). ✅ verified 2026-09-30
- [PromptWizard](https://arxiv.org/abs/2405.18369) — Microsoft's task-aware optimizer: self-evolving critique-and-synthesis loop over instructions and examples (Agarwal et al., 2024). Code: microsoft/PromptWizard. ✅ verified 2026-09-30
- [DSPy Optimizers](https://dspy.ai) — Programmatic prompt optimization (COPRO, MIPRO): compile declarative LM pipelines against a metric. ✅ verified 2026-09-30
- [OpenAI Evals](https://github.com/openai/evals) — OpenAI's framework for evaluating LLMs and LLM systems with YAML-defined evals. ✅ verified 2026-09-30
- [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness) — EleutherAI's standard harness for few-shot evaluation of language models. ✅ verified 2026-09-30
- [HELM](https://github.com/stanford-crfm/helm) — Stanford CRFM's holistic evaluation of language models across scenarios and metrics. ✅ verified 2026-09-30
- [PromptBench](https://github.com/microsoftarchive/promptbench) — Microsoft's benchmark for prompt robustness: attacks, defenses, and prompt variations. (Archived.) ✅ verified 2026-09-30
- [DeepEval](https://github.com/confident-ai/deepeval) — Open-source LLM evaluation framework: unit-test-style evals with 14+ research-backed metrics. ✅ verified 2026-09-30
- [Chain-of-Thought Hub](https://github.com/FranxYao/chain-of-thought-hub) — Benchmark suite measuring chain-of-thought reasoning across math, science, and symbolic tasks. ✅ verified 2026-09-30
## Guides & playbooks

- [OpenAI Prompt Engineering Guide](https://platform.openai.com/docs/guides/prompt-engineering) — OpenAI's official playbook: the six strategies for getting better results. ✅ verified 2026-09-30
- [Anthropic Prompt Engineering Docs](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview) — Anthropic's Claude docs: prompt structure, chaining prompts, and long-context tips. ✅ verified 2026-09-30
- [Google Prompt Engineering Whitepaper](https://www.kaggle.com/whitepaper-prompt-engineering) — Lee Boonstra's 68-page practitioner whitepaper (Google/Kaggle): techniques from zero-shot to ReAct. ✅ verified 2026-09-30
- [Learn Prompting](https://learnprompting.org) — Free, open-source course covering beginner to advanced prompting. ✅ verified 2026-09-30
- [Prompt Engineering Guide (DAIR.AI)](https://promptingguide.ai) — Community reference for prompting techniques, papers, and model-specific notes. ✅ verified 2026-09-30
- [Lil'Log: Prompt Engineering](https://lilianweng.github.io/posts/2023-03-15-prompt-engineering/) — Lilian Weng's deep, well-referenced tour of prompting research. ✅ verified 2026-09-30
- [A Prompt Pattern Catalog](https://arxiv.org/abs/2302.11382) — Reusable prompt patterns for ChatGPT: personas, recipes, templates, and games (White et al., 2023). ✅ verified 2026-09-30
- [Brex Prompt Engineering Guide](https://github.com/brexhq/prompt-engineering) — Brex's public playbook: structured outputs, grounding, and production prompting. ✅ verified 2026-09-30
- [Awesome ChatGPT Prompts](https://github.com/f/prompts.chat) — Community-curated collection of ChatGPT system prompts across roles and tasks. ✅ verified 2026-09-30
- [OpenAI Cookbook](https://github.com/openai/openai-cookbook) — OpenAI's example code and guides, including many prompt-engineering patterns. ✅ verified 2026-09-30
## Papers & surveys

- [Pre-train, Prompt, and Predict](https://arxiv.org/abs/2107.13586) — Foundational survey of prompting methods in NLP (Liu et al., 2021). ✅ verified 2026-09-30
- [A Systematic Survey of Prompt Engineering in Large Language Models](https://arxiv.org/abs/2402.07927) — 44 techniques across application areas with per-task performance summaries (2024). ✅ verified 2026-09-30
- [The Prompt Report](https://arxiv.org/abs/2406.06608) — Taxonomy of 58 prompting techniques from 1,500+ papers plus meta-analysis (Schulhoff et al., 2024). ✅ verified 2026-09-30
- [Why Johnny Can't Prompt](https://doi.org/10.1145/3544548.3581388) — CHI 2023 study: how non-experts actually design prompts - and fail (Zamfirescu-Pereira et al.). ✅ verified 2026-09-30
- [DSPy: Compiling Declarative Language Model Calls into Self-Improving Pipelines](https://arxiv.org/abs/2310.03714) — The DSPy paper: separate program from prompt, optimize programmatically (Khattab et al., 2023). ✅ verified 2026-09-30
- [Prompting Is Programming (LMQL)](https://arxiv.org/abs/2212.06094) — A query language for LLMs with constraints and control flow (Beurer-Kellner et al., 2022). ✅ verified 2026-09-30
- [A Systematic Survey of Prompt Engineering on Vision-Language Foundation Models](https://arxiv.org/abs/2307.12980) — Prompting for Flamingo, CLIP, Stable Diffusion and friends (Gu et al., 2023). ✅ verified 2026-09-30
## Prompt security

- [Indirect Prompt Injection](https://arxiv.org/abs/2302.12173) — 'Not what you've signed up for': compromising real-world LLM-integrated apps via indirect injection (Greshake et al., 2023). ✅ verified 2026-09-30
- [Simon Willison: Prompt Injection Series](https://simonwillison.net/series/prompt-injection/) — Ongoing field notes on prompt-injection attacks and defenses. ✅ verified 2026-09-30
- [OWASP Top 10 for LLM Applications](https://owasp.org/www-project-top-10-for-large-language-model-applications/) — Security risks for LLM apps, starting with LLM01 prompt injection. ✅ verified 2026-09-30

## Related

Part of the [Awesome-llms-labs](https://github.com/awesome-llms-labs) family:

| Repository |
|---|
| [awesome-decisions-llms](https://github.com/awesome-llms-labs/awesome-decisions-llms) |
| [awesome-fast-llms](https://github.com/awesome-llms-labs/awesome-fast-llms) |
| [awesome-flagship-llms](https://github.com/awesome-llms-labs/awesome-flagship-llms) |
| [awesome-flash-llms](https://github.com/awesome-llms-labs/awesome-flash-llms) |
| [awesome-free-llms](https://github.com/awesome-llms-labs/awesome-free-llms) |
| [awesome-ai-agents](https://github.com/awesome-llms-labs/awesome-ai-agents) |
| [awesome-ai-sandboxes](https://github.com/awesome-llms-labs/awesome-ai-sandboxes) |
| [awesome-jev](https://github.com/awesome-llms-labs/awesome-jev) |
| [awesome-microVM](https://github.com/awesome-llms-labs/awesome-microVM) |

## Contributing

Contributions welcome! Please read [CONTRIBUTING.md](CONTRIBUTING.md) first — one entry per bullet, official sources only, and tag verification honestly.

## License

[MIT](LICENSE)
