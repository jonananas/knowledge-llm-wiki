---
type: concept
tags: [software-engineering, ai-agents, automation, developer-tools]
updated: 2026-10-27
---

# Software Factories

A software factory is a system for making software production repeatable by encoding reusable knowledge, tools, processes, and quality controls around development. The term predates generative AI. Current usage often extends the same production-system idea by assigning parts of the work to AI agents.

The shared idea is not simply "generate lots of code." A factory converts defined inputs into validated software artifacts through a repeatable process. The pre-AI and AI-inclusive definitions differ primarily in who or what performs the reasoning between stages.

## Two Definitions

| Aspect | Pre-AI software factory | AI-inclusive or agentic software factory |
|---|---|---|
| Primary mechanism | Templates, reusable components, product-line architectures, domain-specific models, code generators, build systems, and prescribed workflows | The same foundations plus LLM agents that can plan, inspect repositories, implement, debug, test, review, and coordinate work |
| Typical input | Structured configuration, models, templates, or choices within a known application family | Natural-language requirements, product documents, issues, repository state, and machine-readable constraints |
| Main reasoning actor | Human architects and developers | Humans plus probabilistic agents acting as planners, workers, reviewers, or orchestrators |
| Automation profile | Mostly deterministic and bounded to predefined variation points | Adaptive and able to attempt novel changes, but nondeterministic and prone to drift |
| Quality model | Encoded architecture, reusable tested components, build checks, and human engineering practice | Tests and static checks plus agent evaluation, isolation, budgets, traceability, independent review, and human approval |
| Central risk | Rigidity, high setup cost, or forcing unsuitable work into a standardized product line | Scaling plausible but wrong changes, correlated producer-reviewer errors, runaway cost, unreadable output, and review overload |

### Pre-AI Definition

Before generative AI, the term described industrialized software development: capture architectural knowledge and repeated engineering decisions in reusable assets, then automate predictable parts of producing related systems. A [2006 Microsoft description](https://learn.microsoft.com/en-us/archive/msdn-magazine/2006/december/service-station-web-service-software-factory) treated software factories as collections of tools, reusable code, documentation, reference implementations, templates, wizards, and automated recipes that helped teams follow accepted patterns and predefined standards.

In this definition, the factory does not independently understand a product request. Human architects define the product family, allowed variations, reference architecture, and automation. Human developers supply judgment and implement the parts outside the encoded path.

### AI-Inclusive Definition

An AI-inclusive software factory retains the surrounding production system but inserts coding agents into steps that previously required human interpretation. A high-level requirement can be decomposed into tasks; agents can work in isolated branches or sandboxes; automated and agent-based reviewers can evaluate the result; and the system can produce a pull request or deployment candidate.

The model is not the factory. A coding agent is a worker, an [[loop-engineering|agent loop]] is comparable to a workstation, and the factory is the whole delivery system: intake, specifications, orchestration, context, tools, execution environments, version control, verification, approval, cost control, and audit trails.

[[graph-engineering-explained-in-8min]] illustrates one orchestration shape: a task-specific graph that fans work out to specialized agents and later merges their results. Its research example is a DAG; using many nodes raises coordination and token costs, and a verification phase still needs credible evidence rather than a vote count alone.

## Continuity and Discontinuity

AI does not replace the older definition so much as extend it.

The continuity is standardization: both definitions try to encode good practice, reuse proven machinery, and make outcomes more predictable. The discontinuity is that LLMs can operate between deterministic steps. They interpret ambiguous text and unfamiliar code rather than only expanding a template or transforming a formal model.

That flexibility widens the range of work a factory can attempt, but it weakens predictability. The AI-inclusive factory therefore needs stronger external controls, not fewer: bounded tasks, explicit acceptance criteria, isolated workspaces, independent verification, budget and runtime limits, reviewable diffs, and human gates for consequential actions.

## Ronacher's Failure Case

[[astra-for-coding-why-are-we-doing-this-again]] describes an autonomy-heavy experiment in which [[gpt-6-astra]] chose how to organize its workflow, managed its context and notes, and created subagents. The setup emphasized model discretion rather than a predetermined production line with externally designed stages and qualitative gates.

The experiment is therefore not evidence against the historical factory idea or every AI-inclusive implementation. It is evidence that a collection of persistent agents does not become a reliable factory merely by producing code, tests, and commits.

Its main failure was confusing activity with validated progress. Roughly 75,000 net lines and 79 commits accumulated without a useful result. Local signals such as continuing the task, passing narrow checks, or producing another artifact did not capture global coherence, maintainability, or whether the project should stop.

## Design Implications for AI-Inclusive Factories

- Define throughput as accepted, reviewable change rather than tokens, lines of code, tasks, or commits.
- Apply [[review-backpressure]] to scheduled coding loops so new PRs do not accumulate beyond human review capacity. [[loop-engineering-from-first-principles]]
- Keep requirements and acceptance criteria outside the producing agent's control.
- Use independent verification where possible; a model grading its own work can reproduce the same blind spots.
- Bound time, cost, iterations, scope, and diff size in the control system.
- Separate disposable tool code from code that will remain in the repository.
- Check codebase conventions, readability, architecture, and operational risk in addition to functional tests.
- Preserve logs, Git history, artifacts, and approval decisions so a human can reconstruct what happened.
- Stop and escalate when the approach repeatedly fails instead of treating persistence as progress.

These requirements connect software factories to [[spec-driven-ai-development]], [[loop-engineering]], [[agent-loop-guardrails]], [[sandboxed-code-execution]], and the [[verifier-bottleneck]].

## Related Pages

- [[astra-for-coding-why-are-we-doing-this-again]]
- [[gpt-6-astra]]
- [[spec-driven-ai-development]]
- [[loop-engineering]]
- [[graph-engineering]]
- [[agent-loop-guardrails]]
- [[review-backpressure]]
- [[verifier-bottleneck]]
- [[sandboxed-code-execution]]

## Follow-ups

- [ ] [Microsoft Web Service Software Factory](https://learn.microsoft.com/en-us/archive/msdn-magazine/2006/december/service-station-web-service-software-factory) - ingest a primary historical example of the pre-AI definition.
- [ ] [Factory software-factory documentation](https://docs.factory.ai/) - ingest one contemporary product definition of an AI-inclusive factory.
