# AI Code Search at Scale: Finding Method Invocations with Natural Language

Source URL: https://moderne.ai/blog/ai-code-search-at-scale-finding-method-invocations-with-natural-language
Fetch date: 2026-08-27

Authors: Justine Gehring and Kyle Roth
Published: 2024-08-21

Related links:
- OpenRewrite Find method usages: https://docs.openrewrite.org/recipes/java/search/findmethods
- OpenRewrite method patterns: https://docs.openrewrite.org/reference/method-patterns
- Moderne guide: https://docs.moderne.io/user-documentation/moderne-platform/how-to-guides/how-to-find-method-invocations-based-on-a-pattern/
- BAAI/bge-small-en-v1.5: https://huggingface.co/BAAI/bge-small-en-v1.5
- SmartComponents/bge-micro-v2: https://huggingface.co/SmartComponents/bge-micro-v2
- CodeLlama 7B: https://huggingface.co/codellama/CodeLlama-7b-hf

## Summary

The Moderne post describes an AI-powered OpenRewrite recipe for finding method invocations from a natural-language description across many repositories. The motivating example is impact analysis before an IAM migration: the team needed to find all code paths that set a particular authorization header, even though different teams used different HTTP libraries such as Spring WebClient, OkHttp3, and Spring HttpHeaders.

The key idea is to avoid brute-force AI analysis over every method invocation. Moderne uses deterministic code analysis to collect and deduplicate method signatures, ranks those signatures against the natural-language query with embeddings, limits the search to the top-k method patterns, then runs a chain of models from faster to slower to decide whether candidate invocations match the query.

## Main points

- Text search and manually written method-pattern search work only when the developer knows enough about the APIs in use.
- OpenRewrite's `FindMethods` recipe can find method calls accurately when given a type-aware method pattern.
- Large codebases make brute-force AI code search expensive. The post gives an example of 1,218 repositories and roughly 365K method invocations; even at 10 searches per second, a single brute-force search would take about 10 hours.
- Moderne reduces the search space with a two-phase pipeline:
  1. Accumulate and deduplicate method signatures using an OpenRewrite scanning recipe.
  2. Rank signatures by embedding similarity to the user's natural-language query, then revisit only files that contain top-k methods.
- After search-space reduction, the pipeline uses model chaining. Faster, smaller models decide easy cases; harder cases defer to larger models.
- The embedding ranking uses BAAI/bge-small-en-v1.5 in the described implementation.
- The model chain described uses SmartComponents/bge-micro-v2 first, BAAI/bge-large-en-v1.5 second, and CodeLlama 7B as a final generative yes/no decider.
- The final generative model predicts whether two items are related using the probability that the next generated word is "yes."
- Moderne optimized model thresholds with simulated annealing while balancing latency, false positive rate, and false negative budget.
- The authors prefer accepting some ambiguous extra results over missing likely matches because the task is discovery and impact analysis.
- A handwritten test set of method invocations and matching queries is treated as essential for validating thresholds.
- The user-facing recipe is "Find method invocations that resemble a pattern." The recommended query style is precise and concise, often noun-phrase-like, such as "HTTP request with an authorization header."
- Top-K controls the speed/coverage tradeoff: higher values examine more method patterns and run longer.
- Moderne can show matching snippets and file locations, then generate a YAML recipe using exact method patterns from the AI results.

## Interpretation

The post's strongest engineering lesson is not "use an LLM to search code." It is "use static analysis to make AI code search tractable." OpenRewrite supplies the type-aware substrate: method invocations, signatures, method patterns, scanning recipes, and code locations. AI is used where the user lacks precise API knowledge: mapping a natural-language behavior to likely method signatures and judging ambiguous candidates.

This is a practical hybrid architecture for AI developer tooling: deterministic analysis for scale and precision, embeddings for candidate prioritization, and generative models as a limited final decision layer.

## Links

- Blog post: https://moderne.ai/blog/ai-code-search-at-scale-finding-method-invocations-with-natural-language
- OpenRewrite FindMethods: https://docs.openrewrite.org/recipes/java/search/findmethods
- OpenRewrite method patterns: https://docs.openrewrite.org/reference/method-patterns
- Moderne AI method search guide: https://docs.moderne.io/user-documentation/moderne-platform/how-to-guides/how-to-find-method-invocations-based-on-a-pattern/
