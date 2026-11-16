---
type: entity
tags: [ai, language-models, coding-agents, openai]
updated: 2026-11-16
---

# GPT-6 Astra

GPT-6 Astra is the model evaluated by [[armin-ronacher]] in [[astra-for-coding-why-are-we-doing-this-again]]. Ronacher describes it as highly capable at computer use, images, complex topics, reverse engineering, and sustained work, while questioning its fit for human-maintained software engineering.

In the reported experiment, Astra was allowed to manage context, maintain agent notes, and create subagents while pursuing an ambitious CPython language-design task. Its persistence produced a large volume of code and commits, but Ronacher found the outcome unusable and identified recurring problems with readability, codebase conventions, and long-horizon drift.

The [[supra-3d-physag3d]] repository documents a separate use: its released 3D-asset controller currently requires `gpt-6-astra` at high reasoning effort for an agent-assisted geometry and simulation workflow. This is a project configuration, not evidence of comparative model quality.

In [[sparks-of-weight-space-programming]], MIT CSAIL researchers report that Astra could read, repair, and write neural network weights directly. Examples include identifying a policy's game from its parameters, editing 0.016% of Qwen3.5-0.8B to break reasoning loops, and writing working MinAtar policies from zero weights. The authors call this [[weight-space-programming]]. The tool and forward-pass harnesses varied by experiment, and some experiments failed.

## Evidence Status

This page currently combines a critical third-party practitioner account, one project's declared model dependency, and one research group's capability demonstrations. Together these are not a balanced model evaluation. Official documentation and controlled comparative evidence should be ingested before drawing general conclusions about the model.

## Related Pages

- [[armin-ronacher]]
- [[software-factories]]
- [[loop-engineering]]
- [[agent-loop-guardrails]]
- [[physag3d]]
- [[weight-space-programming]]

## Follow-ups

- [ ] [OpenAI model guidance for GPT-6 Astra](https://developers.openai.com/api/docs/guides/latest-model) - capture official capabilities, recommended usage, limitations, and controls.
- [ ] [Building games with Astra](https://developers.openai.com/blog/how-to-build-games-with-astra) - compare the source's acknowledged strength in visual application generation with its software-engineering critique.
