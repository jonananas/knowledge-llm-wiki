---
type: entity
tags: [ai-agents, specs, software-libraries, developer-tools]
updated: 2026-08-26
---

# whenwords

`whenwords` is Drew Breunig's spec-only relative time formatting library. It ships a specification, language-agnostic tests, and agent-oriented installation instructions rather than implementation code. [[a-software-library-with-no-code]]

## Functions

The article says `whenwords` defines five functions:

- `timeago`
- `duration`
- `parse_duration`
- `human_date`
- `date_range`

## Design Significance

`whenwords` is intentionally small and stable enough to test the idea of [[spec-only-libraries]]. It depends on a well-defined standard, Unix time, and has behavior that can be captured in a compact spec plus input/output tests.

## Related Pages

- [[spec-only-libraries]]
- [[spec-driven-ai-development]]
- [[drew-breunig]]

## Follow-ups

- [ ] [whenwords GitHub repository](https://github.com/dbreunig/whenwords) - ingest the repository as a separate source.
