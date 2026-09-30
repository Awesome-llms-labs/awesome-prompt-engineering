# Evaluating Prompts

Prompt changes are code changes: they deserve tests.

## Build a golden set

Collect 20–100 representative inputs with expected outputs (or grading rubrics). Cover the common cases *and* the edge cases you actually care about. Version it alongside your prompts.

## Exact checks first, judges second

- **Deterministic checks** where possible: exact match, regex, JSON-schema validation, unit tests on extracted values.
- **LLM-as-judge** for open-ended quality: use a strong model with a written rubric, and spot-check its grades against humans. Judges have biases (verbosity, position) — calibrate before trusting.
- **Pairwise / Elo** for subjective tasks where no single right answer exists.

## Regression-test in CI

Run the golden set on every prompt change. Tools: [Promptfoo](https://promptfoo.dev), [DeepEval](https://github.com/confident-ai/deepeval), [OpenAI Evals](https://github.com/openai/evals), [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness). Track pass rate over time in [Langfuse](https://langfuse.com/docs) or [LangSmith](https://www.langchain.com/langsmith).

## Optimize against the metric

Once you have a metric, automate the search:
- **Discrete optimizers**: [APE](https://arxiv.org/abs/2211.01910), [OPRO](https://arxiv.org/abs/2309.03409), [Promptbreeder](https://arxiv.org/abs/2309.16797), [ProTeGi](https://arxiv.org/abs/2305.03495), [PromptWizard](https://arxiv.org/abs/2405.18369).
- **Programmatic**: [DSPy optimizers](https://dspy.ai) compile pipelines against your metric instead of editing strings.

## Know when to stop

Diminishing returns are real: once changes move the metric less than its noise floor, stop tuning and fix the task framing, the data, or the model instead. Re-evaluate on a held-out set — optimizers overfit golden sets just like models overfit training data.
