# Glossary

- **System prompt** — the persistent instruction block that sets role, rules, and output format for a conversation or API call.
- **Few-shot / zero-shot** — prompting with a handful of examples vs. with none.
- **Chain-of-thought (CoT)** — prompting the model to reason step by step before answering.
- **Self-consistency** — sampling several reasoning paths and taking the majority answer.
- **In-context learning** — the model adapting to examples or instructions given in the prompt, without weight updates.
- **Prompt chaining** — splitting a task into sequential prompts where each step's output feeds the next.
- **Structured output** — constraining generation to a schema (JSON, regex, grammar) so outputs are machine-parseable.
- **Temperature / top-p** — sampling controls trading creativity for determinism; not a substitute for a good prompt.
- **Prompt injection** — malicious instructions smuggled into model input (user content, tool output, documents) that override intended behavior.
- **Indirect prompt injection** — the injection arrives via third-party content the model retrieves, not the user directly.
- **Eval / golden set** — a fixed set of inputs with expected outputs (or rubrics) used to score prompt changes.
- **LLM-as-judge** — using a model to grade outputs against a rubric; useful but biased, needs calibration.
- **Prompt optimizer** — a method that searches for better prompts automatically (e.g. APE, OPRO, DSPy optimizers).
- **Prompt registry** — versioned storage for prompts with release labels, diffing, and rollback (PromptLayer, Langfuse, LangSmith).
- **Tokens** — the billing and context-window unit; longer prompts and reasoning traces cost more.
