---
type: entity
tags: [ai-agents, agent-harness, sdk, open-source]
updated: 2026-11-16
---

# OpenWorker

OpenWorker is an MIT-licensed agent project hosted at [github.com/andrewyng/openworker](https://github.com/andrewyng/openworker), with docs at [openworker.com](https://openworker.com/docs/sdk/). It includes a desktop app built on a Python engine and a Harness SDK built on a Rust engine for embedding agents in other applications. [[andrewyng-openworker-harness]]

## Harness SDK at a Glance

- TypeScript (`@openworkerai/harness-sdk`) and Rust SDKs over one Rust engine.
- Agent loop, streaming, cancellation, context compaction, and durable sessions stored in SQLite or PostgreSQL.
- Approvals, session grants, guardrails, hooks, and OpenShell isolation for shell and file execution.
- Sub-agents and teams with durable messages and boards; opt-in tracing with export to Langfuse.
- OpenAI Responses API by default; any Responses-compatible endpoint works, including local providers.
- A builder skill installs SDK guidance into Claude Code or Codex projects.

The API is still evolving, and the cloud deployment guides are experimental.

## Related Pages

- [[agent-harnesses]]
- [[agent-loop-guardrails]]
- [[sandboxed-code-execution]]
