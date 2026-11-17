---
type: source
tags: [ai-agents, agent-harness, sdk, rust, typescript]
updated: 2026-11-16
source_url: https://github.com/andrewyng/openworker/blob/main/harness/README.md
---

# andrewyng/openworker: Harness SDK

Source: [harness/README.md in andrewyng/openworker](https://github.com/andrewyng/openworker/blob/main/harness/README.md), viewed 2026-11-16. Raw capture: [raw/andrewyng-openworker-harness.md](../../raw/andrewyng-openworker-harness.md).

## Summary

The README presents the [[openworker]] Harness SDK as a way to embed tool-using, delegating agents inside an application without building the [[agent-harnesses|agent harness]] yourself. The application keeps the UI, authentication, model and tool choice, and policies. OpenWorker runs the agent loop, model calls, approvals, and durable sessions. A single Rust engine powers both a TypeScript SDK, which runs it as a child process, and a Rust SDK, which can embed it in-process.

## Key Takeaways

- **The harness is a library, not a product.** The split of responsibilities is explicit: the application owns identity and policy, and the harness owns loop mechanics. That makes the agent a component inside your app rather than a separate assistant.
- **Durable sessions with careful recovery.** Sessions survive restarts. Recovery deliberately avoids replaying actions whose outcome is unknown, and the README says to reconcile unknown tool outcomes before retrying.
- **Human control is part of the design.** The SDK provides per-operation approvals, session grants, optional LLM-assisted review, guardrails, and hooks. Agent identity is immutable: changing instructions, tools, or approvals requires a new agent name, which keeps runs auditable.
- **The README is candid about isolation.** OpenShell isolates configured shell and file execution, but application callbacks run with the app's privileges, and a workspace path alone does not confine filesystem access. Credentials and state should stay out of model-readable files.
- **The recommended setup is a skill for coding agents.** `npx @openworkerai/openworker-harness-builder --agent claude|codex` installs SDK instructions and examples into a project for [[claude-code]] or Codex, instead of asking developers to read the docs themselves.
- **Early-stage maturity.** The API is evolving and SDK pull requests are on hold. The cloud deployment guides are experimental, and the README contains no evaluation or benchmarks.

## Connections

- [[openworker]]: the project.
- [[agent-harnesses]]: the general pattern of a runtime that wraps a model in a loop with tools, state, and controls.
- [[agent-loop-guardrails]]: approvals, hooks, guardrails, and careful handling of unknown outcomes.
- [[sandboxed-code-execution]]: OpenShell isolation, and the warning that callbacks are not sandboxed.
- [[magnitude]]: another agent runtime that supports local and OpenAI-compatible endpoints.

## Follow-ups

- [ ] [OpenWorker SDK docs](https://openworker.com/docs/sdk/): sessions, tools, guardrails, and the provider list in more depth.
- [ ] [OpenShell guide](https://github.com/andrewyng/openworker/tree/main/docs/harness/guides): find out what OpenShell actually is and what its isolation guarantees cover.
- [ ] [OpenWorker repository root](https://github.com/andrewyng/openworker): the Desktop App and its separate Python engine.
