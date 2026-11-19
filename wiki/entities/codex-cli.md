---
type: entity
tags: [ai-agents, coding-agents, cli, openai]
updated: 2026-11-17
---

# Codex CLI

Codex CLI is OpenAI's open-source (Apache-2.0) local coding agent, developed at [github.com/openai/codex](https://github.com/openai/codex). The same agent is available as a CLI, an IDE extension (VS Code, Cursor, Windsurf), a desktop app, and a cloud agent (Codex Web). Users sign in with a ChatGPT plan (recommended) or an API key. [[openai-codex]]

`@openai/codex-sdk` and the Python SDKs drive the CLI programmatically. The TypeScript SDK spawns the binary and exchanges JSONL events, with persistent resumable threads, streaming events, and JSON Schema output. [[openai-codex]]

Other uses in the wiki: [[supra-3d-physag3d]] uses it as a controller runtime, and [[openworker]]'s builder skill can install SDK guidance into Codex projects.

## Related Pages

- [[claude-code]]
- [[agent-harnesses]]
- [[gpt-6-astra]]
- [[openworker]]
