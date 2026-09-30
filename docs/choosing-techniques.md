# Choosing Prompting Techniques

A practical decision order. Start simple; add complexity only when the simple thing fails on your eval set.

## 1. Baseline: zero-shot with a clear task frame

Write the instruction plainly: what to do, what the output should look like, and any hard constraints. Most failures at this stage are underspecification, not model weakness. See [Why Johnny Can't Prompt](https://doi.org/10.1145/3544548.3581388) for how non-experts typically go wrong.

## 2. Few-shot examples

Add 2–5 input→output examples when the output format or style matters. Keep them diverse and correct — wrong examples teach wrong patterns. Prefer examples with more reasoning steps for hard tasks ([Complexity-Based Prompting](https://arxiv.org/abs/2210.00720)).

## 3. Chain-of-thought for reasoning

When the task needs multi-step reasoning (math, logic, planning), ask for intermediate steps. Zero-shot CoT ("let's think step by step") is free to try; few-shot CoT with worked examples is stronger. Add [Self-Consistency](https://arxiv.org/abs/2203.11171) (sample several paths, majority vote) when accuracy matters more than latency.

## 4. Decomposition for complex tasks

If one prompt can't hold the whole task, break it up:
- **Least-to-Most**: solve easier subproblems first, feed answers forward.
- **Prompt chaining**: sequential steps, each a focused prompt; validate intermediate outputs.
- **Plan-and-Solve**: have the model write the plan before executing it.

## 5. Tools and code for precision

When the model must compute, look things up, or act: use [ReAct](https://arxiv.org/abs/2210.03629) (interleaved reasoning + actions), [PAL](https://arxiv.org/abs/2211.10435) (write code, execute it), or [ReWOO](https://arxiv.org/abs/2305.18323) (plan all tool calls upfront to save tokens).

## 6. Search and self-correction for hard problems

[Tree of Thoughts](https://arxiv.org/abs/2305.10601) / [Graph of Thoughts](https://arxiv.org/abs/2308.09687) explore multiple reasoning branches; [Self-Refine](https://arxiv.org/abs/2303.17651) and [Reflexion](https://arxiv.org/abs/2303.11366) iterate with feedback. These multiply cost — reserve them for tasks where a wrong answer is expensive.

## 7. Stop hand-tuning; start optimizing

Once a technique family works, switch to programmatic optimization ([DSPy](https://github.com/stanfordnlp/dspy), [APE](https://arxiv.org/abs/2211.01910), [OPRO](https://arxiv.org/abs/2309.03409)) against a real eval set instead of tweaking wording by feel.
