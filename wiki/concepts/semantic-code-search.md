---
type: concept
tags: [code-search, ai, developer-tools, static-analysis]
updated: 2026-08-27
---

# Semantic Code Search

Semantic code search is code search driven by meaning rather than exact strings or symbols. A user can describe behavior in natural language, and the system tries to find code that implements or invokes that behavior.

The [[moderne-ai-code-search-at-scale]] source shows a constrained version for method invocations. A user describes a method behavior, such as "HTTP request with an authorization header"; the system embeds the query and method signatures, ranks likely candidates, then uses model chaining to judge whether candidate invocations match.

## Practical Pattern

- Use static analysis to extract structured code facts.
- Use embeddings to map natural-language intent to likely code entities.
- Use top-k selection to bound cost.
- Use stronger models only on ambiguous candidates.
- Return deterministic artifacts such as method patterns, snippets, file locations, or generated recipes.

## Risk

Semantic code search can miss relevant cases or return ambiguous false positives. For discovery and impact analysis, the Moderne post explicitly prefers tolerating some false positives over missing important candidates. That tradeoff should be calibrated with tests, thresholds, and review. [[moderne-ai-code-search-at-scale]]

## Related Pages

- [[moderne-ai-code-search-at-scale]]
- [[type-aware-code-search]]
- [[openrewrite]]
- [[large-scale-code-remediation]]
- [[moderne]]
