# Practical Loop Engineering

Source URL: https://addyosmani.com/blog/practical-loop-engineering/
Author: Addy Osmani
Published: 2026-08-14
Captured: 2026-10-27

## Main Points

- A loop is an agent feedback cycle that acts, checks the result, and adjusts until a defined goal is met. Osmani describes four operating modes: human-directed turns, bounded goals, interval-based loops, and proactive scheduled or event-driven routines.
- A goal suits a specific task with a measurable finish line and finite retry bound. Specify the measurement tool and stop after stalled progress.
- A recurring loop is a scheduler for repeated checks or changing external inputs, such as new issues, PR comments, or CI failures. A scheduled cloud routine can outlive a local session. A recurring trigger can start a bounded goal for each item of work.
- Verification must be stronger than the agent's own confidence. The article recommends direct interaction with UI changes, checking browser errors and performance, and using a separate reviewer for generated code. Osmani says the goal evaluator checks whether specified hard rules were met in the conversation; it does not judge the work's overall quality.
- Human judgment remains necessary for taste, product value, architecture, and sensitive areas such as authentication, security, or finance. Osmani recounts nearly accepting agent-generated competitor-inspired changes that would have added user complexity for little benefit.
- Repeated attempts without a changed result are a signal to stop. Open-ended creative work and vague goals such as making a UI "good" are poor fits for unattended loops.
- Examples include daily PR and issue triage, reviewing against contribution rules, and combining a periodic issue check with a bounded fix. The article describes these as personal practices and illustrative prompts, not measured evidence that the workflows improve outcomes.

## Product Details Reported in the Article

- Osmani presents Claude Code `/goal` as a bounded task primitive, `/loop` as a local recurring prompt, and `/schedule` as a cloud routine. These are product-specific descriptions from the August 2026 article and should be verified against current official documentation before use.
- The article says local recurring loops are session-scoped and expire after seven days; a cloud schedule persists separately. Treat these lifecycle details as time-sensitive.

## Notable Links

- Claude Code team loop write-up: https://x.com/ClaudeDevs/article/2074208949205881033
- Ralph loop by Geoff Huntley: https://ghuntley.com/loop/
