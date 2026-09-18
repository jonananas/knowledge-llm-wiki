---
type: concept
tags: [ai-agents, software-development, specs, developer-tools]
updated: 2026-09-16
---

# Spec Driven AI Development

Spec-driven AI development is a workflow where the human writes or maintains explicit specifications, tests, constraints, and acceptance criteria, then uses coding agents to generate or modify implementation code against those checks.

The [[a-software-library-with-no-code]] source gives a concrete example: [[whenwords]] ships a detailed spec and language-agnostic tests, then asks a coding agent to create the implementation in the target language and run tests until they pass.

## Why It Matters

Spec-driven AI development shifts human work away from typing code and toward defining behavior, test oracles, constraints, and boundaries. It is closely related to [[agent-loop-guardrails]] because good specs and tests provide the pass/fail signals agents need.

In [[software-factories]], the specification is part of the externally governed production system rather than something the implementing agent should freely redefine. [[astra-for-coding-why-are-we-doing-this-again]] also shows the limit of behavioral specification alone: passing tests may not capture readability, architectural fit, or reviewer burden, so those qualities need separate gates.

## Open Questions

- How detailed must a spec be before generated code is reliable?
- Which domains are simple enough for generated local implementations?
- How should teams test changes across multiple agents, languages, and generated variants?
- How should support work when each user may have a different generated implementation?
- Where is a maintained reference implementation still necessary?

## Related Pages

- [[spec-only-libraries]]
- [[whenwords]]
- [[agent-loop-guardrails]]
- [[ai-developer-tools]]
- [[software-factories]]
