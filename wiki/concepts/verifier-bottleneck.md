---
type: concept
tags: [ai, science, verification, evaluation]
updated: 2026-09-16
---

# Verifier Bottleneck

The verifier bottleneck is the constraint created when candidate generation becomes cheap but reliable verification remains expensive, slow, scarce, or institutionally weak.

The [[ai-is-doing-something-weird-to-science]] source argues that this is the central problem AI creates for science. Better proposers create more candidate claims, but science only advances when verifiers can separate valid discoveries from plausible noise.

## Why It Matters

- LLMs can generate many plausible hypotheses, proofs, papers, or design candidates.
- Weak verification lets confident nonsense scale.
- Academic peer review was not designed for a world where plausible candidate generation is cheap.
- Paper count, citation count, and journal prestige become worse proxies when generation is cheap.
- The scarce skill shifts to posing the right question and building a reliable verifier.

## Diagnostic Question

When evaluating an AI-in-science result, ask: what was the verifier, and who built it?

Reliable verifiers include formal proof checkers, physical experiments, crystallography, pre-registered replication, or measurements with known error bars. A model judging its own plausibility is not enough. [[ai-is-doing-something-weird-to-science]]

## Software Engineering

The same bottleneck appears in [[software-factories|AI-inclusive software factories]]. Agents can generate code, tests, and commits faster than humans can understand architectural consequences or verify maintainability. [[astra-for-coding-why-are-we-doing-this-again]] is a qualitative example: artifact production scaled for 35 hours, while reliable judgment of whether the overall direction was useful did not.

Functional tests cover only part of this verifier. Production software also needs review of readability, codebase conventions, architecture, security, operational behavior, and whether the change should exist at all. If generation throughput rises faster than this review capacity, the factory creates a review backlog rather than engineering value.

## Related Pages

- [[ai-in-science]]
- [[proposer-verifier-curator-loop]]
- [[verification-driven-agent-knowledge]]
- [[software-factories]]
- [[agent-loop-guardrails]]
