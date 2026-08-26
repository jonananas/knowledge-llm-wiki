---
type: concept
tags: [ai-agents, safety, automation, developer-tools]
updated: 2026-08-26
---

# Agent Loop Guardrails

Agent loop guardrails are the controls that keep an autonomous or semi-autonomous agent loop bounded, verifiable, affordable, and reversible.

The [[fltman-loop-engineer]] source gives a five-point checklist for every scaffolded loop: verifiable exit condition, hard max-iteration cap, budget cap in code, sandboxed working environment, and human checkpoint for irreversible actions.

## Checklist

- Verifiable exit condition: checked each iteration by a machine-readable signal.
- Max-iteration cap: enforced in code, not only requested in a prompt.
- Budget cap: the loop sums cost and stops before the next model call would cross the limit.
- Sandbox: the loop runs in a worktree, container, or branch rather than unattended on the main branch.
- Human checkpoint: pushes, deploys, sends, deletes, or other irreversible actions require approval.

## Why They Matter

Agent loops can fail by running forever, optimizing a vague proxy, spending more than expected, modifying the wrong workspace, or taking irreversible actions without review. Guardrails turn a loop from "keep trying" into a controlled system with known exit paths. [[fltman-loop-engineer]]

## Related Pages

- [[loop-engineering]]
- [[loop-engineer]]
- [[sandboxed-code-execution]]
