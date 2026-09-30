# Contributing

Thanks for helping keep this the most current directory of prompt engineering resources!

## Adding an entry

1. **Check it fits:** a prompting *technique* (few-shot, CoT, ReAct, …), a prompt *framework/library* (DSPy, Guidance, Outlines, …), prompt *tooling/platforms* (versioning, observability, playgrounds), prompt *evaluation/optimization* methods, a high-quality *guide/playbook*, a key *research paper/survey*, or prompt *security* resources. This list stays scoped to prompt engineering — general LLM lists belong in the sibling repos (see Related in the README).
2. **Add to the right section** of `README.md` and keep sections in their existing order.
3. **One entry = one bullet.** Format:
   `- [Name](https://official-site-or-repo) — ` one-line description.
   Tag verification honestly: write `✅ verified YYYY-MM-DD` only when you checked the claim on the official page/repo/arXiv yourself; otherwise mark it `⚠️ unverified`.
4. **Add the matching record** to `data/prompt-engineering.json` with these exact fields:

| field | type | values |
|---|---|---|
| `name` | string | technique, framework, tool, method, guide, or paper title |
| `url` | string | official https:// URL (docs, repo, or arXiv abstract) |
| `description` | string | one sentence, no invented specs |
| `category` | string | `technique` / `framework` / `tooling` / `evaluation` / `guide` / `paper` / `security` |
| `verified` | bool | `true` only if you verified it on an official source |
| `verified_date` | string | `YYYY-MM-DD` of verification, or `""` |
| `verified_source` | string | where you verified it (e.g. `arXiv API`, `GitHub API`, `HTTP 200 via curl`), or `""` |

5. **Keep CI green:** JSON schema is validated and all Markdown links are checked with lychee on every push.

## Reporting issues

Stale link, superseded technique, or a better source? Open an issue — include the replacement URL.
