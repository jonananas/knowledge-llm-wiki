---
type: source
tags: [ai-agents, loop-engineering, claude-code, verification]
updated: 2026-10-27
source_url: https://addyosmani.com/blog/practical-loop-engineering/
---

# Practical Loop Engineering

Source: [Addy Osmani, August 14, 2026](https://addyosmani.com/blog/practical-loop-engineering/). Raw capture: [raw/practical-loop-engineering.md](../../raw/practical-loop-engineering.md).

## Summary

[[addy-osmani]] describes [[loop-engineering]] as designing the feedback cycle around an agent: what starts a run, what result counts as success, how it is checked, and when work stops or returns to a human. The article is a practitioner account of using several agents and Claude Code's goal, loop, and schedule primitives, with PR and issue triage as recurring examples.

## Key Takeaways

- **Choose the trigger and stop condition together.** Human-directed turns suit ordinary tasks; a bounded goal suits a measurable piece of work; an interval loop suits repeated checks; a proactive routine suits a stream of defined work. A scheduled check can launch a bounded goal for each item.
- **Specify the verifier and limits.** A target such as a Lighthouse score is stronger when the command producing it, maximum attempts, and lack-of-progress stop rule are explicit. A repeated command with no changed result is a reason to stop and reassess.
- **Keep verification separate from generation.** Osmani recommends an independent checker and direct inspection of the artifact. He says the `/goal` evaluator checks whether hard rules were satisfied in the conversation, not whether the resulting code is good.
- **Retain human product judgment.** Tests and metrics do not decide whether a feature is worth adding, whether complexity is justified, or whether a sensitive change is acceptable. Subjective design and open-ended exploration are poor candidates for unattended loops.
- **Use recurring work as the first candidate.** His own example is reviewing a large PR and issue queue against written contribution rules; the article offers operational examples rather than comparative outcome data.

## Connections

- [[loop-engineering]] — extends the existing taxonomy with a practical distinction between bounded task completion and recurring triggers.
- [[agent-loop-guardrails]] — adds independent artifact review, stalled-progress stops, and attention to sensitive or subjective changes.
- [[claude-code]] — article-specific descriptions of `/goal`, `/loop`, and `/schedule`; verify current syntax and lifecycle in official docs.
- [[verifier-bottleneck]] — objective checks cover only part of code quality and product judgment.
- [[fltman-loop-engineer]] — complementary pattern and guardrail reference; this article focuses more on how a practitioner selects and supervises loops.

## Follow-ups

- [ ] [Claude Code team's loop taxonomy](https://x.com/ClaudeDevs/article/2074208949205881033) — inspect the primary write-up behind the four-mode classification.
- [ ] [Ralph loop](https://ghuntley.com/loop/) — examine the earlier hand-rolled loop pattern Osmani cites.
