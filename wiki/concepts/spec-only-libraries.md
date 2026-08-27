---
type: concept
tags: [software-architecture, ai-agents, specs, open-source]
updated: 2026-08-26
---

# Spec Only Libraries

Spec-only libraries are software libraries distributed as behavior specifications, tests, and implementation instructions rather than as maintained source code.

The [[a-software-library-with-no-code]] source explores this through [[whenwords]], a relative time formatting library that asks coding agents to generate target-language implementations from `SPEC.md` and `tests.yaml`.

## When They May Fit

- The library is a small utility.
- Behavior is stable and compact enough to specify precisely.
- The dependency surface is small.
- Performance is not critical.
- Generated implementations can be tested with language-agnostic input/output cases.
- Users are comfortable auditing or owning the generated code.

## When They Do Not Fit

- Performance matters.
- Test surface grows across many languages, agents, and runtime environments.
- Users need reliable support and reproducible bug reports.
- Security updates or continual compatibility updates matter.
- Community, interoperability, and shared reference behavior are important.

## Relation To Open Source

The article argues that conventional code libraries are more than specs. Mature open source captures bug history, performance work, community review, shared interoperability, and maintained reference behavior. Spec-only libraries may work for implement-and-forget utilities, but foundational dependencies still benefit from code and community. [[a-software-library-with-no-code]]

## Related Pages

- [[whenwords]]
- [[spec-driven-ai-development]]
- [[ai-developer-tools]]
