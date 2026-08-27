---
type: source
tags: [ai-agents, software-architecture, specs, developer-tools]
updated: 2026-08-26
source_url: https://www.dbreunig.com/2026/01/08/a-software-library-with-no-code.html
author: Drew Breunig
published: 2026-01-08
---

# A Software Library with No Code

Source: [dbreunig.com](https://www.dbreunig.com/2026/01/08/a-software-library-with-no-code.html). Raw capture: [raw/a-software-library-with-no-code.md](../../raw/a-software-library-with-no-code.md).

## Summary

Drew Breunig introduces [[whenwords]], a relative time formatting library that ships no implementation code. Instead, it ships a behavior specification, language-agnostic tests, and instructions for asking a coding agent to generate an implementation in the desired language.

The article uses `whenwords` as a concrete thought experiment for [[spec-driven-ai-development]] and [[spec-only-libraries]]. It argues that coding agents make spec-only utility libraries plausible, but also gives a clear boundary: conventional code libraries still matter when performance, complex testing, support, updates, security, interoperability, and community matter.

## Key Takeaways

- `whenwords` ships `SPEC.md`, `tests.yaml`, and `INSTALL.md` rather than source code.
- The generated implementation is expected to pass language-agnostic input/output tests.
- The model works best for simple utilities with stable behavior, small dependency surface, modest performance requirements, and compact specs.
- The article treats coding-agent capability as the enabling change: tightly specified tasks can now be implemented idiomatically across multiple languages.
- Spec-only libraries become difficult when testing must cover many languages, agents, and generated variants.
- Support is harder because generated code can differ across users, agents, model versions, prompts, and environments.
- Foundational dependencies still need maintained code, security updates, bug history, performance work, and community coordination.
- The article's strongest distinction is between implement-and-forget utilities and maintained infrastructure.

## Boundary Conditions

Breunig lists five reasons to still prefer libraries with code:

- Performance matters.
- Testing is complicated.
- Support and bug fixes matter.
- Updates and security patches matter.
- Community and interoperability matter.

These become the practical decision criteria for evaluating any [[spec-only-libraries]] proposal.

## Connections

- [[whenwords]] - artifact released with the article.
- [[drew-breunig]] - author.
- [[spec-only-libraries]] - central concept.
- [[spec-driven-ai-development]] - broader developer workflow connection.
- [[claude-code]] - one coding-agent environment mentioned as capable of implementing the spec.
- [[ai-developer-tools]] - opinion page this source informs.

## Follow-ups

- [ ] [whenwords repository](https://github.com/dbreunig/whenwords) - ingest the actual spec, tests, verification checklist, and README.
- [ ] [whenwords SPEC.md](https://github.com/dbreunig/whenwords/blob/main/SPEC.md) - evaluate what makes the spec agent-implementable.
- [ ] [whenwords tests.yaml](https://github.com/dbreunig/whenwords) - inspect the language-agnostic test shape.
- [ ] [LiteLLM](https://www.litellm.ai/) - capture the maintained-library counterexample used in the article.
