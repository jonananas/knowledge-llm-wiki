---
type: entity
tags: [ai, language-models, coding-agents, openai]
updated: 2026-09-16
---

# GPT-6 Astra

GPT-6 Astra is the model evaluated by [[armin-ronacher]] in [[astra-for-coding-why-are-we-doing-this-again]]. Ronacher describes it as highly capable at computer use, images, complex topics, reverse engineering, and sustained work, while questioning its fit for human-maintained software engineering.

In the reported experiment, Astra was allowed to manage context, maintain agent notes, and create subagents while pursuing an ambitious CPython language-design task. Its persistence produced a large volume of code and commits, but Ronacher found the outcome unusable and identified recurring problems with readability, codebase conventions, and long-horizon drift.

## Evidence Status

This page currently represents a critical third-party practitioner account, not a balanced model evaluation. Official documentation and controlled comparative evidence should be ingested before drawing general conclusions about the model.

## Related Pages

- [[armin-ronacher]]
- [[software-factories]]
- [[loop-engineering]]
- [[agent-loop-guardrails]]

## Follow-ups

- [ ] [OpenAI model guidance for GPT-6 Astra](https://developers.openai.com/api/docs/guides/latest-model) - capture official capabilities, recommended usage, limitations, and controls.
- [ ] [Building games with Astra](https://developers.openai.com/blog/how-to-build-games-with-astra) - compare the source's acknowledged strength in visual application generation with its software-engineering critique.
