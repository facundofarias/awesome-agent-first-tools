# Contributing

Thanks for helping curate **Awesome Agent-First Tools**. The value of this list is its focus, so the bar is intentionally high.

## The one rule that matters

> List tools an agent **uses at runtime**. Do not list tools for **building** agents.

If someone would import your project to *construct* an agent (a framework, orchestrator, or SDK for wiring up LLMs), it does **not** belong here. If a running agent would *call* it to get something done — search, browse, execute code, remember, transact, authenticate — it does.

When in doubt, ask: *"Is the primary consumer of this tool a human developer, or an autonomous agent?"* Only agent-consumers qualify.

## Inclusion criteria

A tool should satisfy most of these:

- [ ] **Machine-first interface** — a callable API/protocol, not a GUI a human drives.
- [ ] **LLM-ready output** — structured (JSON/markdown) and token-efficient.
- [ ] **Headless & programmatic** — works with no human in the loop.
- [ ] **Built for LLM failure modes** — sandboxed / idempotent / retryable, self-describing, with actionable errors.
- [ ] **Real and maintained** — shipped, documented, and not abandoned.

## Explicitly out of scope

- Agent frameworks & orchestration (LangChain, CrewAI, AutoGen, LlamaIndex).
- Autonomous agents / copilots (the *agents* themselves).
- Exhaustive MCP server catalogs — link to a dedicated directory instead.
- Prompt libraries, model providers, and generic ML tooling.
- **AI IDEs and coding agents** (Cursor, Windsurf, Claude Code, Devin) — these *are* agents/copilots, not tools an agent calls. The Code & Developer Tools category is only for things an agent invokes at runtime to read, edit, search, or run code (e.g. fast-apply models, code-search APIs, agent-callable VCS).

## How to submit

1. Fork and edit `README.md`.
2. Add your entry to the most fitting category, in the format:
   `- [Tool](https://link) — One sentence on what an agent uses it for.`
3. Keep descriptions to a single, factual sentence. No marketing language.
4. Keep entries alphabetical within a category is *not* required — order by usefulness.
5. In your PR description, state which inclusion criteria the tool meets and who its primary consumer is.

## Affiliated entries

If you have a financial or maintainer relationship with a tool you're submitting, **disclose it** in the PR and add a disclosure note to the entry. Affiliated tools are held to the *same* inclusion criteria as everything else — no exceptions in either direction. Self-promotion that can't stand on the criteria will be rejected; a genuinely agent-first tool won't be excluded just because its author submitted it, as long as the affiliation is transparent.

## Style

- One sentence per entry, ending with a period.
- Link to the canonical project/docs page, not a blog post.
- No duplicate entries across categories — pick the best fit.
