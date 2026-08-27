---
type: entity
tags: [developer-tools, static-analysis, refactoring, java]
updated: 2026-08-27
---

# OpenRewrite

OpenRewrite is a framework for large-scale automated code search and refactoring. In the [[moderne-ai-code-search-at-scale]] source, [[moderne]] uses OpenRewrite scanning recipes to collect method invocation signatures, then uses those signatures as the deterministic substrate for AI-assisted method search.

## Relevant Concepts

- Recipes define searches or transformations.
- Scanning recipes can collect information across a repository before later phases act on it.
- Method patterns provide type-aware matching for method definitions or invocations.
- `FindMethods` can find method calls by method pattern when the receiver type, method name, and argument types are known.

## Why It Matters

OpenRewrite gives AI code-search workflows a precise code model. Instead of asking a model to read every file, a tool can extract typed method invocations, deduplicate signatures, and map AI results back to file locations or generated follow-up recipes. [[moderne-ai-code-search-at-scale]]

## Related Pages

- [[moderne]]
- [[moderne-ai-code-search-at-scale]]
- [[type-aware-code-search]]
- [[semantic-code-search]]
- [[large-scale-code-remediation]]
