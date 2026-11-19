---
type: concept
tags: [ai-agents, agent-harness, architecture]
updated: 2026-11-17
---

# Agent Harnesses

An agent harness is the runtime around a model that turns it into an agent. It runs the model/tool loop, stores conversation state, dispatches tool calls, enforces approvals and guardrails, and handles cancellation, context compaction, and recovery. The model supplies reasoning; the harness supplies everything that makes repeated tool use safe and durable.

## Embedded harness pattern

[[andrewyng-openworker-harness]] packages the harness as an SDK to embed in an application, with a clear split:

- **The application owns** the UI, authentication, user and session ownership, model choice, tool choice, and policy.
- **The harness owns** the agent loop, model calls, approvals, and durable sessions.

Other recurring design points from that source:

- **Durable sessions with careful recovery.** After a crash, an action with an unknown outcome is reconciled rather than blindly replayed.
- **Immutable agent identity.** Changing instructions, tools, or approvals creates a new agent, which keeps runs auditable.
- **Separate trust zones.** The loop runs in a trusted process, shell and file execution run in an isolated sandbox, and application callbacks keep application privileges. A workspace path alone is not a security boundary.
- **Delegation as a primitive.** Sub-agents and teams communicate through durable messages and boards; see [[graph-engineering]].

## Relation to other pages

- Harness controls implement many [[agent-loop-guardrails]], such as approvals, hooks, and budget and iteration limits.
- [[loop-engineering]] covers how to design a particular loop; the harness is the infrastructure it runs on.
- [[claude-code]], [[codex-cli]], and [[magnitude]] are complete agent products with built-in harnesses. OpenWorker exposes its harness as a library for other applications.
- There are two ways to embed an agent. A **general-purpose harness** such as [[openworker]] lets your application define the tools, policies, and identity. A **product wrapper** such as `@openai/codex-sdk` spawns a finished coding agent and streams its events ([[openai-codex]]). The first gives more control; the second inherits a mature, coding-specialized agent.
- The harness also defines what the model is allowed to observe and do, so results depend on it. [[sparks-of-weight-space-programming]] notes that its findings are "limited by harness design".

## Related Pages

- [[openworker]]
- [[codex-cli]]
- [[agent-loop-guardrails]]
- [[sandboxed-code-execution]]
- [[loop-engineering]]
