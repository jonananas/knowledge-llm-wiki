---
type: source
tags: [ai, code-search, static-analysis, developer-tools, refactoring]
updated: 2026-08-27
source_url: https://moderne.ai/blog/ai-code-search-at-scale-finding-method-invocations-with-natural-language
---

# AI Code Search at Scale

Source: [Moderne blog](https://moderne.ai/blog/ai-code-search-at-scale-finding-method-invocations-with-natural-language). Raw capture: [raw/moderne-ai-code-search-at-scale.md](../../raw/moderne-ai-code-search-at-scale.md).

Justine Gehring and Kyle Roth describe how [[moderne]] built a natural-language method-invocation search recipe on top of [[openrewrite]]. The problem is impact analysis across large codebases: before a migration or refactor, developers often need to find behavior such as "HTTP request with an authorization header" without knowing every library and method name used across the organization.

The post is relevant to [[semantic-code-search]], [[type-aware-code-search]], and [[large-scale-code-remediation]] because it shows a hybrid design: deterministic AST/type-aware scanning reduces the search space, embeddings rank likely method signatures, and a model chain handles ambiguous semantic matches.

## Key Points

- Existing [[openrewrite]] method-pattern search is accurate when the method pattern is known, but migration discovery often starts before the developer knows all relevant APIs.
- Brute-force AI search over all invocations is too slow at portfolio scale. The post estimates about 10 hours for one search over 365K method invocations at 10 searches per second.
- Moderne first uses an OpenRewrite scanning recipe to visit all method invocations, collect signatures, and deduplicate them.
- It then embeds the user query and method signatures, ranks by distance, and only revisits files containing top-k candidate method patterns.
- Model chaining runs smaller/faster models first and defers hard cases to slower/larger models.
- The described chain uses `SmartComponents/bge-micro-v2`, `BAAI/bge-large-en-v1.5`, and CodeLlama 7B as a final yes/no decider.
- Thresholds for the model chain are optimized with simulated annealing against accuracy and latency.
- The authors intentionally tolerate some false positives because the task is discovery; missing relevant instances is usually worse than reviewing extra candidates.
- A handwritten test set of method invocations and matching queries is treated as necessary for calibrating thresholds.
- The final workflow can turn AI-discovered method patterns into a deterministic YAML recipe for exact follow-up searches.

## Interpretation

The source is a useful counterweight to naive "AI searches code" framing. The scalable part comes from [[type-aware-code-search]] and static analysis: OpenRewrite can extract real method invocations and method signatures from code, which lets Moderne avoid sending every source snippet through a model.

The AI layer is used narrowly and pragmatically. It helps translate intent into candidate method patterns and judge semantic resemblance, while deterministic tooling keeps the result actionable: snippets, file locations, method patterns, and generated recipes.

## Follow-ups

- [ ] [OpenRewrite Find method usages](https://docs.openrewrite.org/recipes/java/search/findmethods) - capture exact recipe behavior and data tables.
- [ ] [OpenRewrite method patterns](https://docs.openrewrite.org/reference/method-patterns) - capture the type-aware method-pattern syntax.
- [ ] [Moderne AI method search guide](https://docs.moderne.io/user-documentation/moderne-platform/how-to-guides/how-to-find-method-invocations-based-on-a-pattern/) - capture user-facing query guidance and limitations.
- [ ] [Mila](https://mila.quebec/) - inspect the collaboration context mentioned in the blog.

## Related Pages

- [[moderne]]
- [[openrewrite]]
- [[semantic-code-search]]
- [[type-aware-code-search]]
- [[large-scale-code-remediation]]
