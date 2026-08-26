---
type: concept
tags: [ai-agents, automation, developer-tools]
updated: 2026-08-26
---

# Loop Engineering

Loop engineering is the design of autonomous or semi-autonomous agent loops: when an agent runs, what prompts it, what it observes, how it verifies progress, when it stops, and when it hands control back to a human.

The [[fltman-loop-engineer]] source frames loop engineering as a shift in the developer's attention from code, to the agent, to the surrounding loop that controls the agent.

## Pattern Taxonomy From Loop Engineer

- Headless while-loop: one agent iterates against one binary check.
- Evaluator-optimizer: one component generates work while a separate critic evaluates quality.
- Meta or prompt-refinement: a loop improves the prompt that another loop uses.
- Orchestrator fan-out: an orchestrator assigns unpredictable subtasks to worker agents and verifies their results.
- Scheduled or triggered: the loop runs by interval, self-paced command, external trigger, or cloud routine.

## Core Design Question

The source's strongest claim is that a loop without a verifiable exit condition should not exist. A vague objective such as "improve the UX" gives the loop no pass/fail boundary, while a command such as a passing test suite can act as a machine-checkable stop condition. [[fltman-loop-engineer]]

## Knowledge Loops

The [[announcing-stack-overflow-for-agents]] source suggests a broader loop around agent work: search shared knowledge before solving, contribute when a gap is discovered, require human review, then let later agents and developers verify outcomes. This is less about local task control and more about making agent discoveries compound across sessions.

## Science Loops

The [[ai-is-doing-something-weird-to-science]] source generalizes the loop idea to AI-assisted science. It argues that discovery comes from the structure connecting human question selection, model proposal generation, independent verification, and human curation. In that frame, the most important design question is not whether the model is intelligent, but whether the loop has a strong verifier.

## Related Pages

- [[loop-engineer]]
- [[agent-loop-guardrails]]
- [[agent-knowledge-sharing]]
- [[verification-driven-agent-knowledge]]
- [[proposer-verifier-curator-loop]]
- [[verifier-bottleneck]]
- [[sandboxed-code-execution]]
