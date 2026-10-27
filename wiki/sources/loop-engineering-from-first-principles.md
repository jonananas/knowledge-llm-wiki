---
type: source
tags: [ai-agents, loop-engineering, control-theory, code-review, migrations]
updated: 2026-10-27
source_url: https://www.youtube.com/watch?v=xIt_mTQp6mY
---

# Loop Engineering from First Principles

Source: [Kyle Mistele's AI Engineer World's Fair 2026 talk](https://www.youtube.com/watch?v=xIt_mTQp6mY), with [conference transcript and slides](https://ai.engineer/talks/xIt_mTQp6mY-loop-engineering-from-first-principles). Raw capture: [raw/loop-engineering-from-first-principles.md](../../raw/loop-engineering-from-first-principles.md). The control-theory slide is saved at [raw/assets/kyle-mistele-control-loop.webp](../../raw/assets/kyle-mistele-control-loop.webp).

## Summary

[[kyle-mistele]] argues that a useful coding-agent loop should make small, measurable, reviewable corrections to a changing codebase. A prompt repeated without a sensor, selection policy, and feedback can create a huge PR even if other agents review it. He illustrates the alternative with [[humanlayer]]'s incremental RPC-to-Effect migration.

## Control-Loop Mapping

| Control-theory part | Coding-loop example |
|---|---|
| Set point | Desired codebase property: RPC procedures use the target pattern. |
| Sensor | Structural scan finds remaining unmigrated procedures. |
| Measured error | Sorted, version-controlled list of violations. |
| Controller | Chooses a small next target, such as the smallest procedure. |
| Actuator | Coding agent applies the migration using a skill and hand-written golden patterns. |
| System | Repository and its CI/review workflow. |
| Disturbance | Other developers adding or changing code during the migration. |
| Feedback | Deterministic CI, PR review, and a new scan after the change. |

## Operational Details

- Record a baseline of existing violations on `main`; reject new violations in PRs while reducing the old backlog. This prevents concurrent work from reversing progress.
- Prefer deterministic scanning and target selection when possible. Use agent judgment where it adds value, especially in implementing the correction.
- Run one iteration in existing CI, then publish a small PR for human review. A version-controlled feedback file and an `/iterate` PR comment let review guidance improve the current proposal and later runs.
- Label PRs by loop and check for an earlier open PR before starting another iteration. This [[review-backpressure|backpressure]] keeps generation aligned with review capacity.
- Increase batch size or parallel review ownership only after the loop's outputs are reliably reviewable. The talk does not quantify the benefit of these extensions.

## Connections

- [[loop-engineering]] — gives the existing concept a concrete sensor/controller/actuator model and production migration example.
- [[review-backpressure]] — stops a scheduled loop when its prior PR is still awaiting review.
- [[agent-loop-guardrails]] — adds limits on change size, new violations, and outstanding PRs.
- [[software-factories]] and [[verifier-bottleneck]] — generated output is useful only at a rate humans and checks can absorb.
- [[practical-loop-engineering]] — Osmani's complementary account emphasizes choosing bounded versus recurring loops and retaining independent judgment.

## Follow-ups

- [ ] [HumanLayer agent skills](https://github.com/humanlayer/skills) — inspect the published control-loop design skill and compare its implementation with the talk.
- [ ] [ast-grep rule configuration](https://ast-grep.github.io/guide/rule-config.html) — capture structural sensing options for codebase migrations.
