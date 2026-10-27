---
type: concept
tags: [ai-agents, automation, developer-tools]
updated: 2026-10-27
---

# Loop Engineering

Loop engineering is the design of autonomous or semi-autonomous agent loops: when an agent runs, what prompts it, what it observes, how it verifies progress, when it stops, and when it hands control back to a human.

The [[fltman-loop-engineer]] source frames loop engineering as a shift in the developer's attention from code, to the agent, to the surrounding loop that controls the agent.

[[practical-loop-engineering]] adds a practitioner's selection rule: use human-directed turns for ordinary work, a bounded goal for a measurable finish line, an interval loop for recurring checks, and a scheduled or event-driven routine for a continuing stream. A recurring trigger may start a separate bounded goal for each new item. The article describes Claude Code primitives for these modes; their exact syntax and lifecycle are product details to verify in current documentation.

## Control-Theory Model

[[loop-engineering-from-first-principles]] maps a coding loop to a changing system under feedback. The codebase has a desired property (set point). A sensor measures violations, a controller chooses a small correction, an actuator agent makes the change, and CI plus review measure the result. Other team changes are disturbances that the loop must tolerate. The model is useful when a discrepancy can be measured and corrected incrementally.

Mistele's RPC-to-Effect migration makes the model concrete: ast-grep produces a stable violation list, a deterministic controller chooses a small procedure, and an agent works from hand-written golden patterns. A baseline check prevents new violations while the old ones are cleared. Each iteration yields a reviewable PR, then the codebase is measured again. A loop should also apply [[review-backpressure]] so scheduled work stops while its previous PR awaits review.

## Relation to Workflow Graphs

[[graph-engineering-explained-in-8min]] uses a parallel research DAG to illustrate [[graph-engineering]]: separate nodes perform requirements, topic selection, information gathering, verification, and synthesis, with edges carrying work between phases. A loop can be one node's internal behavior or a cycle in a larger graph. The video's DAG is one possible workflow shape, while loop engineering focuses on repeated feedback and stopping conditions.

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

## Software Factories

An individual loop can act as one station inside [[software-factories|an AI-inclusive software factory]]. The factory adds intake, task routing, shared context, isolated workspaces, multiple worker or reviewer roles, version control, approvals, and delivery around one or more loops.

[[astra-for-coding-why-are-we-doing-this-again]] provides a negative case for treating persistence as loop quality. Its autonomy-heavy experiment continued for about 35 hours and produced a large volume of code without a useful result. A verifiable local exit condition is therefore necessary but not sufficient: the surrounding system also needs scope, cost, architectural-quality, reviewability, and escalation controls.

Osmani makes the same distinction from daily practice: a goal evaluator can check stated hard rules, while an independent reviewer and the human owner still need to inspect the artifact and decide whether the change is worth making. [[practical-loop-engineering]]

## Related Pages

- [[loop-engineer]]
- [[addy-osmani]]
- [[kyle-mistele]]
- [[review-backpressure]]
- [[graph-engineering]]
- [[agent-loop-guardrails]]
- [[agent-knowledge-sharing]]
- [[verification-driven-agent-knowledge]]
- [[proposer-verifier-curator-loop]]
- [[verifier-bottleneck]]
- [[sandboxed-code-execution]]
- [[software-factories]]
