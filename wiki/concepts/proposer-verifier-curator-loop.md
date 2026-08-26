---
type: concept
tags: [ai, science, verification, loops]
updated: 2026-08-26
---

# Proposer Verifier Curator Loop

The proposer-verifier-curator loop is a model of AI-assisted discovery where different roles are kept distinct:

- Poser: asks the question.
- Proposer: generates candidate solutions.
- Verifier: independently filters candidates for correctness.
- Curator: selects which verified results are worth pursuing, publishing, or trusting.

In [[ai-is-doing-something-weird-to-science]], this loop is used to explain why both "AI did the science" and "AI is just autocomplete" are too simple. AI can contribute essential surprising candidates while still not being the verifier, question-poser, curator, or accountable author.

## Examples From The Source

- Claude's Cycles: Claude proposed, Stappers curated explorations, Knuth verified by hand.
- Tao and Lean: LLMs propose proof steps, Lean verifies proof terms, humans curate directions.
- AlphaFold: model proposes structures, physical experiments verify them, humans choose what matters.
- GNoME/A-Lab: model proposes crystal structures, automated synthesis and measurement verify candidates.

## Design Rule

Do not let the proposer act as the verifier. If the same model generates a claim and judges its plausibility without an independent check, the loop is not closed. [[ai-is-doing-something-weird-to-science]]

## Related Pages

- [[ai-in-science]]
- [[verifier-bottleneck]]
- [[loop-engineering]]
