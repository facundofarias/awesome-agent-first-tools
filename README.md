# Awesome Agent-First Tools [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of tools built to be used **by AI agents** — not frameworks for building them.

An *agent-first tool* is software whose **primary consumer is an autonomous agent, not a human**. It exposes a machine-first interface, returns structured and token-efficient output, runs headless by default, and is designed around how LLMs actually fail (sandboxing, idempotency, capability discovery, clear structured errors).

This list is deliberately narrow. If a project helps you *build* an agent, it belongs elsewhere. If an agent *reaches for it at runtime* — to search, browse, execute code, remember, transact, or authenticate — it belongs here.

**What counts as agent-first?** A tool earns a spot when it does most of these:

- **Machine-first interface** — an API/protocol an agent can call directly, not a GUI a human drives.
- **LLM-ready output** — structured (JSON/markdown), token-efficient, not raw HTML meant for a browser.
- **Headless & programmatic** — usable with no human in the loop.
- **Built for LLM failure modes** — sandboxed, idempotent, retryable, with self-describing schemas and actionable errors.

**Not on this list:**

- **Agent frameworks & orchestration** (LangChain, CrewAI, AutoGen, LlamaIndex) → try [awesome-ai-agents](https://github.com/e2b-dev/awesome-ai-agents).
- **The agents themselves** (autonomous apps, copilots).
- **General MCP server directories** → try [awesome-mcp-servers](https://github.com/punkpeye/awesome-mcp-servers). We list protocols and a few reference servers, not every integration.

## Contents

- [Interop Protocols](#interop-protocols)
- [Web Search & Retrieval](#web-search--retrieval)
- [Web Scraping & Browsing](#web-scraping--browsing)
- [Code Execution & Sandboxes](#code-execution--sandboxes)
- [Code & Developer Tools](#code--developer-tools)
- [Storage & Media](#storage--media)
- [Memory](#memory)
- [Auth & Tool-Calling Infrastructure](#auth--tool-calling-infrastructure)
- [Communication](#communication)
- [Payments & Commerce](#payments--commerce)
- [Observability & Evaluation](#observability--evaluation)

## Interop Protocols

The plumbing that makes any tool agent-consumable.

- [Model Context Protocol (MCP)](https://modelcontextprotocol.io) - Open standard for connecting agents to tools and data through a uniform client/server interface.
- [llms.txt](https://llmstxt.org) - A proposed standard for websites to expose an LLM-friendly, markdown summary of their content at `/llms.txt`.
- [A2A (Agent2Agent)](https://a2a-protocol.org) - Open protocol for agents from different vendors to discover each other's capabilities and collaborate.
- [x402](https://x402.org) - Open protocol that revives the HTTP 402 "Payment Required" status code for agent-native payments: agents pay per request in stablecoins, no accounts or human in the loop.

## Web Search & Retrieval

Search APIs that return LLM-ready results instead of a page of blue links.

- [Exa](https://exa.ai) - Neural/embeddings search API built for agents, with content retrieval and similarity search.
- [Tavily](https://tavily.com) - Search API purpose-built for LLMs and RAG, returning concise, sourced answers.
- [Linkup](https://linkup.so) - Search API that returns grounded answers with citations from the live web.
- [Jina Reader](https://jina.ai/reader) - Prepend `r.jina.ai/` to any URL to get clean, LLM-ready markdown of the page.

## Web Scraping & Browsing

Turn the live web into structured data an agent can act on.

- [Firecrawl](https://firecrawl.dev) - Crawl and scrape any site into clean markdown or structured JSON for LLMs.
- [Browserbase](https://browserbase.com) - Headless browser infrastructure for agents, with [Stagehand](https://stagehand.dev) for AI-driven browser actions.
- [Playwright MCP](https://github.com/microsoft/playwright-mcp) - MCP server exposing a real browser to agents via structured accessibility snapshots.
- [browser-use](https://github.com/browser-use/browser-use) - Library that lets agents control a browser through natural-language tasks.

## Code Execution & Sandboxes

Safe, ephemeral compute for agent-generated code.

- [E2B](https://e2b.dev) - Secure, isolated cloud sandboxes for running AI-generated code, with an SDK built for agent workflows.
- [Daytona](https://daytona.io) - Fast, disposable dev environments/sandboxes designed for AI agent code execution.
- [Modal](https://modal.com) - Serverless compute for running arbitrary code and functions on demand, popular as an agent execution backend.
- [Cloudflare Sandbox SDK](https://github.com/cloudflare/sandbox-sdk) - Run untrusted, agent-generated code in isolated containers on Cloudflare's edge.

## Code & Developer Tools

Tools an agent invokes while reading, editing, searching, or running code. Excludes AI IDEs and coding agents themselves (Cursor, Claude Code, Devin) — those are agents, not tools an agent reaches for.

- [Morph](https://morphllm.com) - Fast apply model that merges an LLM's suggested edits into source files at thousands of tokens per second.
- [Relace](https://relace.ai) - Fast apply and code-editing models plus codebase retrieval, built for AI coding agents.
- [Greptile](https://greptile.com) - Codebase understanding and AI code review that answers questions and reviews PRs over a whole repository via API.
- [GitHub MCP Server](https://github.com/github/github-mcp-server) - Official MCP server exposing GitHub issues, PRs, code, and Actions as agent tool calls.
- [Sourcegraph](https://sourcegraph.com) - Code search and navigation across large codebases, exposed through APIs and an MCP server for agents to query.

## Storage & Media

Store, transform, and serve files and assets through an agent-callable interface.

- [PixelVault](https://pixelvault.dev) - Agent-first image hosting API with an MCP server and installable agent skill: upload, batch, transform, sign, and CDN-deliver images programmatically. *(Disclosure: built by this list's maintainers; see [CONTRIBUTING.md](CONTRIBUTING.md#affiliated-entries).)*
- [Fastio](https://fast.io/storage-for-agents/) - Cloud storage built for agents, with an MCP server and installable skill for file upload, retrieval, versioning, and semantic search.

## Memory

Persistent state and recall across sessions, built for LLMs.

- [Mem0](https://mem0.ai) - Memory layer that extracts, stores, and retrieves per-user/agent facts across conversations.
- [Zep](https://getzep.com) - Long-term memory and a temporal knowledge graph for agents, with fast retrieval.
- [Letta](https://letta.com) - Stateful agents server (formerly MemGPT) with self-editing memory that persists beyond the context window.

## Auth & Tool-Calling Infrastructure

Let agents act inside third-party systems, safely.

- [Arcade](https://arcade.dev) - Handles OAuth and authenticated tool calls so agents can act as a user across services.
- [Composio](https://composio.dev) - Managed integrations and tool-calling for 1,000+ apps (500+ pre-built toolkits) with built-in delegated auth for agents.
- [Toolhouse](https://toolhouse.ai) - Hosted tools and infrastructure agents can call without custom integration work.

## Communication

Give agents their own channels — email, messaging, voice — to send and receive on their own.

- [AgentMail](https://agentmail.to) - API-first email provider for agents: programmatic inboxes, an MCP server, SDKs, and IMAP/SMTP so agents can send, receive, and manage email autonomously.
- [AgentPhone](https://agentphone.ai) - Gives agents their own US/Canada phone number for voice and SMS via an MCP server, SDKs, and REST, so they can call and text without a human in the loop.
- [AgentCall](https://agentcall.co) - Phone-number API for agents with SMS, OTP auto-extraction, and multilingual AI voice, exposed as a hosted MCP server and REST API.

## Payments & Commerce

Infrastructure for agents that transact.

- [Stripe Agent Toolkit](https://github.com/stripe/ai) - Lets agents create payments, issue cards, and manage billing through Stripe.
- [Skyfire](https://skyfire.xyz) - Payment and identity rails purpose-built for autonomous agent-to-agent and agent-to-service transactions.
- [Payman](https://paymanai.com) - API for agents to send and request real-world payments with human approval controls.

## Observability & Evaluation

Trace, debug, and score how agents use their tools.

- [Langfuse](https://langfuse.com) - Open-source tracing, evals, and analytics for LLM and agent applications.
- [Helicone](https://helicone.ai) - Observability proxy that logs, caches, and monitors agent LLM/tool calls with one header. *(Maintenance mode after Mintlify acquisition, 2026.)*
- [Braintrust](https://braintrust.dev) - Evaluation and monitoring platform for iterating on agent and LLM behavior.

## Contributing

Contributions are welcome! Read [CONTRIBUTING.md](CONTRIBUTING.md) first — the inclusion bar is deliberately strict to keep this list focused on tools agents *use*, not tools for *building* agents.

To the extent possible under law, contributors have waived all copyright and related rights to this work ([CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/); see [LICENSE](LICENSE)).
