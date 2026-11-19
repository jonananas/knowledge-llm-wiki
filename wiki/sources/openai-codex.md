---
type: source
tags: [ai-agents, coding-agents, cli, sdk, openai]
updated: 2026-11-17
source_url: https://github.com/openai/codex
---

# openai/codex

Source: [openai/codex repository README](https://github.com/openai/codex) and its [TypeScript SDK README](https://github.com/openai/codex/blob/main/sdk/typescript/README.md), viewed 2026-11-17. Raw capture: [raw/openai-codex.md](../../raw/openai-codex.md).

## Summary

The repository hosts [[codex-cli]], OpenAI's open-source (Apache-2.0) coding agent that runs locally in a terminal. The same agent is also available as an IDE extension, a desktop app, and a cloud agent. Users can sign in with a ChatGPT plan, which the README recommends, or with an API key. An `sdk/` folder provides TypeScript and Python SDKs that drive the CLI programmatically.

## Key Takeaways

- **It's a product first and an SDK second.** The README covers installation and sign-in; sandboxing, approvals, configuration, and MCP are left to the [docs site](https://developers.openai.com/codex).
- **The SDK wraps the CLI.** `@openai/codex-sdk` spawns the `codex` binary and exchanges JSONL events over stdin and stdout. Embedding Codex therefore means embedding the whole coding agent, with its built-in tools and policies, rather than a generic agent loop.
- **Threads, streaming, and structured output.** Threads persist in `~/.codex/sessions` and can be resumed by ID. `runStreamed()` emits typed events, and `outputSchema` constrains a turn to a JSON Schema.
- **Built for coding.** The working directory must be a Git repo by default, and sandbox and permission behavior is set through Codex config overrides rather than custom application callbacks.
- **Mature and widely used.** The repo had about 135k stars and over 13k commits on the capture date, with installers for every major platform, which contrasts with early-stage SDKs such as [[openworker]].

## Connections

- [[codex-cli]]: the product.
- [[agent-harnesses]]: Codex is a complete agent with a built-in harness, and the SDK exposes it by wrapping the CLI.
- [[andrewyng-openworker-harness]]: an alternative for embedding agents in applications; [[openworker]] supports a Codex builder skill.
- [[gpt-6-astra]], [[astra-for-coding-why-are-we-doing-this-again]]: a critical account of long-running coding with OpenAI models.
- [[supra-3d-physag3d]]: uses Codex CLI as its controller runtime.

## Follow-ups

- [ ] [Codex docs](https://developers.openai.com/codex): sandbox modes, approval policies, `AGENTS.md` and config, MCP, and non-interactive exec mode.
- [ ] [Python SDK](https://github.com/openai/codex/tree/main/sdk/python): check whether it also wraps the CLI and how it differs from `python-runtime`.
- [ ] [Codex auth with API key](https://developers.openai.com/codex/auth#sign-in-with-an-api-key): what changes for server-side or multi-user deployments.
