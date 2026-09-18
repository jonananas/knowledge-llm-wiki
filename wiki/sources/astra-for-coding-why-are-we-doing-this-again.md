---
type: source
tags: [ai-agents, coding-agents, software-engineering, code-quality]
updated: 2026-09-16
source_url: https://lucumr.pocoo.org/2026/9/7/astra-why/
author: Armin Ronacher
published: 2026-09-07
license: CC-BY-NC-4.0
---

# Astra for Coding: Why Are We Doing This Again?

Source: [Armin Ronacher's blog](https://lucumr.pocoo.org/2026/9/7/astra-why/). Raw capture: [raw/astra-for-coding-why-are-we-doing-this-again.md](../../raw/astra-for-coding-why-are-we-doing-this-again.md).

## Summary

[[armin-ronacher]] reports on using [[gpt-6-astra]] for coding, including a 35-hour, deliberately hands-off [[software-factories|AI-inclusive software-factory]] experiment. He finds the model highly capable and unusually persistent, but poorly aligned with the human qualities expected of durable software: readable edits, codebase-native style, coherent architecture, bounded scope, and economical use of reviewer attention.

His central hypothesis is that long-horizon completion and token-efficient tool use are rewarded more clearly than maintainability and human comprehension. Dense disposable code used for tool calls then appears to leak into repository code, while an unattended multi-agent run continues producing artifacts after its overall direction has become unproductive.

## Key Takeaways

- Greater autonomy and longer task horizons can amplify weak quality signals rather than correct them.
- Tool-call code and committed code have different quality requirements; optimizing both for compact execution can damage the maintained artifact.
- Passing narrow tests, producing commits, and continuing to work are not sufficient measures of useful engineering progress.
- The experiment generated roughly 75,000 net lines and 79 commits over about 35 hours, but Ronacher judged that it delivered nothing useful.
- The article later estimates about one billion tokens and USD 1,200 in raw API costs; an earlier passage separately estimates that the exhausted ChatGPT reset allowance represented about four billion tokens.
- Human readability and reviewability need to be explicit system objectives because they are difficult to capture with simple automated metrics.
- Cheap generation moves the bottleneck toward verification, architectural judgment, and review.

## What "Software Factory" Means Here

The source uses the contemporary AI-inclusive meaning of [[software-factories]]: a system in which a model manages context, organizes work, creates subagents, edits code, tests results, and maintains working notes over a long-running task.

This is not the full historical meaning of software factory. Pre-AI software factories centered on standardizing repeated development through reusable components, templates, reference architectures, code generation, tooling, and prescribed processes. AI-inclusive factories extend that lineage by placing probabilistic agents inside the production system as planners, implementers, debuggers, or reviewers.

Ronacher's setup intentionally maximized model discretion. It should therefore be treated as evidence about an under-governed, autonomy-heavy factory experiment, not as evidence that all software factories share the same architecture or failure mode.

## Failure Modes Observed

- Dense Python string manipulation was used to patch C files instead of the harness's editing tools.
- Tool chains became difficult to inspect, including Bash invoking Python, Python invoking Node.js, and Node.js invoking PowerShell.
- Compressed formatting appeared in committed tests and implementation code.
- Generated code introduced magic numeric indexes, hardcoded operation identifiers, and styles foreign to the surrounding CPython codebase.
- Internal task structure and notes became progressively harder to understand during the long run.
- The system kept producing work without recognizing that the global approach had failed.

## Interpretation and Limits

This is a detailed practitioner account, not a controlled benchmark. The target was an ambitious interpreter and language-design project, and Ronacher explicitly acknowledges that the hands-off prompting setup was poor. His claims about training incentives are informed speculation rather than documented model-training facts.

The article is most useful as a catalog of qualitative failure modes and as negative evidence for the claim that model persistence plus subagent delegation is sufficient for reliable software production. It strengthens the case for [[loop-engineering]], [[agent-loop-guardrails]], and independent verification, while showing that tests and completion criteria alone may not capture maintainability or architectural quality.

## Connections

- [[armin-ronacher]] - author and operator of the experiment.
- [[gpt-6-astra]] - model evaluated in the article.
- [[software-factories]] - historical and AI-inclusive concept used to frame the experiment.
- [[loop-engineering]] - design of the control system around long-running agents.
- [[agent-loop-guardrails]] - runtime, budget, scope, and human-review controls implicated by the failure.
- [[verifier-bottleneck]] - generation scaled far beyond the demonstrated capacity to validate useful output.
- [[spec-driven-ai-development]] - complementary emphasis on externally maintained specifications and acceptance criteria.

## Follow-ups

- [ ] [From Async/Await to Virtual Threads](https://lucumr.pocoo.org/2025/7/26/virtual-threads/) - capture the technical goal that the factory attempted to explore.
- [ ] [Codex shell-command parser](https://github.com/openai/codex/blob/f1aac1e885f676a1129f2da0c46a3dba86392fc6/codex-rs/shell-command/src/parse_command.rs) - investigate the distinction between visible tool operations and shell commands recognized by the harness.
