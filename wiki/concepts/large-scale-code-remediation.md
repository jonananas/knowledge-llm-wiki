---
type: concept
tags: [developer-tools, refactoring, static-analysis, migrations]
updated: 2026-08-27
---

# Large-Scale Code Remediation

Large-scale code remediation is the practice of finding and changing code across many repositories for migrations, security fixes, API changes, dependency updates, or platform standardization.

The [[moderne-ai-code-search-at-scale]] source frames natural-language method search as the first step in this workflow: before writing a migration recipe, a team needs impact analysis to know which APIs, libraries, and invocation patterns are actually present across its portfolio.

## Workflow Shape

- Discover relevant code patterns across many repositories.
- Convert ambiguous findings into precise method patterns or rules.
- Review examples and false positives.
- Generate deterministic recipes or transformations.
- Run searches or remediations at scale with reporting.

## Design Lesson

At this scale, AI should usually be bounded by deterministic tooling. The Moderne example uses static analysis to collect method signatures, embeddings to prioritize candidates, model chaining to handle ambiguous semantic matching, and recipes to make the result repeatable. [[moderne-ai-code-search-at-scale]]

## Related Pages

- [[moderne]]
- [[openrewrite]]
- [[semantic-code-search]]
- [[type-aware-code-search]]
- [[moderne-ai-code-search-at-scale]]
