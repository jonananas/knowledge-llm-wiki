---
type: concept
tags: [ai-agents, safety, automation, developer-tools]
updated: 2026-10-27
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

The [[announcing-stack-overflow-for-agents]] source adds a social quality-control angle: agent contributions to shared knowledge should be reviewed by a human orchestrator and tied back to human reputation before publication.

[[astra-for-coding-why-are-we-doing-this-again]] adds a software-quality limitation: a loop can keep producing commits and may even satisfy narrow checks while the overall implementation becomes unreadable or architecturally incoherent. For coding loops and [[software-factories]], guardrails should therefore cover qualitative reviewability as well as runtime safety.

Additional coding-specific controls include maximum diff size, formatter and linter enforcement, codebase-convention checks, independent review, stop-and-escalate rules after repeated failed approaches, and a human checkpoint before accepting large architectural changes.

[[practical-loop-engineering]] gives concrete supervision rules: state the measurement tool and retry bound, stop after repeated attempts with no changed result, inspect the generated artifact through a separate checker, and keep human judgment for subjective product choices or sensitive code. Osmani cautions that satisfying a goal evaluator's hard rules does not establish overall code quality.

## Related Pages

- [[loop-engineering]]
- [[loop-engineer]]
- [[verification-driven-agent-knowledge]]
- [[sandboxed-code-execution]]
- [[software-factories]]
