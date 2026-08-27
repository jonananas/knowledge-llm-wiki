---
type: concept
tags: [code-search, static-analysis, developer-tools, refactoring]
updated: 2026-08-27
---

# Type-Aware Code Search

Type-aware code search uses parsed and typed program structure rather than plain text. For method search, this means matching receiver type, method name, and argument types instead of only matching characters in source files.

The [[moderne-ai-code-search-at-scale]] source relies on [[openrewrite]] method patterns as this exact-search layer. OpenRewrite's method patterns can match method definitions or invocations accurately when the method pattern is known, making them useful for impact analysis and follow-up remediation after an AI-assisted discovery step.

## Why It Matters

Plain text search is fast but noisy and brittle. Type-aware search can distinguish overloads, constructors, receiver types, and argument types. It can also feed structured downstream workflows such as generated recipes, data tables, and automated refactors.

## Relationship To AI

The Moderne post uses AI to discover candidate method patterns, not to replace type-aware matching. Once likely methods are found, type-aware search becomes the reliable mechanism for rerunning, reviewing, and operationalizing the results.

## Related Pages

- [[openrewrite]]
- [[moderne-ai-code-search-at-scale]]
- [[semantic-code-search]]
- [[large-scale-code-remediation]]
