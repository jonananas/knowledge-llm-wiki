---
type: entity
tags: [ai-agents, claude-code, developer-tools, automation]
updated: 2026-08-26
---

# Loop Engineer

Loop Engineer is a Claude Code skill and subagent pack from the `fltman/loop-engineer` GitHub repository. It helps users choose, scaffold, teach, and audit guarded agentic loops. [[fltman-loop-engineer]]

## What It Contains

- `loop-engineer` skill: knowledge pack with decision tree, references, guardrails, and templates.
- `loop-architect` subagent: interactive designer that forces the goal into a binary form, chooses a loop pattern, scaffolds files, and wires guardrails.
- `loop-teacher` subagent: interactive tutor for learning loop engineering before scaffolding.
- Slash commands: `/new-loop`, `/loop-audit`, and `/learn-loops`.
- Templates for headless loops, evaluator-optimizer loops, prompt-refinement loops, orchestrator fan-out loops, and `/goal`/`/loop` recipes.

## Design Stance

Loop Engineer treats the dangerous part of agent loops as control design rather than model prompting. Its README puts the strongest emphasis on stopping conditions, cost caps, sandboxing, and human checkpoints before a loop runs unattended. [[fltman-loop-engineer]]

## Related Pages

- [[loop-engineering]]
- [[agent-loop-guardrails]]
- [[claude-code]]
