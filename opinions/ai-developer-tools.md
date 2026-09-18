# AI Developer Tools

Updated: 2026-09-16

This page tracks working opinions about AI developer tools. These are not treated as established conclusions unless supported by cited source pages.

## Current Opinions

- Spec-driven AI development is more structured and probably more successful than just prompting.
- [[loop-engineering]] is possibly the next step after spec-driven AI development; evaluation needed.
- An AI-inclusive [[software-factories|software factory]] should be treated as a governed delivery pipeline, not as an autonomous code-volume engine. Its useful throughput is accepted, reviewable change rather than tokens, lines, commits, or agent runtime.

## Current Evidence Status

The vault currently has source-backed notes on adjacent tools and concepts: [[a-software-library-with-no-code]], [[spec-driven-ai-development]], [[spec-only-libraries]], [[whenwords]], [[fltman-loop-engineer]], [[loop-engineering]], [[agent-loop-guardrails]], [[stack-overflow-for-agents]], [[agent-knowledge-sharing]], [[verification-driven-agent-knowledge]], [[proposer-verifier-curator-loop]], [[verifier-bottleneck]], [[codesandbox]], [[sandboxed-code-execution]], [[magnitude]], [[local-agent-inference]], [[moderne]], [[openrewrite]], [[semantic-code-search]], [[type-aware-code-search]], [[large-scale-code-remediation]], [[wordpress-playground]], [[browser-local-software]], [[fumadocs]], and [[uv]].

It does not yet contain enough comparative evidence to support the claim that spec-driven AI development is more successful than prompting, or that loop engineering is the next step. Treat both as hypotheses.

The [[announcing-stack-overflow-for-agents]] source is relevant but still indirect: it supports the need for verification, shared knowledge, and human-reviewed agent outputs, not the stronger claim that a particular development workflow is superior.

The [[ai-is-doing-something-weird-to-science]] source is also indirect but useful for the loop-engineering hypothesis: it argues that AI value depends less on raw model output and more on the surrounding proposer/verifier/curator loop.

The [[a-software-library-with-no-code]] source directly supports the spec-driven AI development hypothesis as a concrete thought experiment: tightly specified behavior plus language-agnostic tests can let coding agents generate working implementations across languages. It also supplies boundaries where this approach is likely weak: performance-critical code, complex testing, support, updates, security, and community interoperability.

The [[moderne-ai-code-search-at-scale]] source supports a more constrained AI developer-tools pattern: AI works best when bounded by deterministic program analysis, test sets, thresholds, and repeatable recipes.

The [[wordpress-everywhere]] source is relevant to AI developer tooling because [[wordpress-playground]] provides fast, browser-local, rollbackable WordPress instances that can serve as safer targets for AI-assisted plugin, theme, and site experiments.

The [[astra-for-coding-why-are-we-doing-this-again]] source is direct but qualitative negative evidence about autonomy-heavy coding workflows. It reports that a 35-hour multi-agent experiment generated a large amount of code and commits without useful output, while compact tool-call habits leaked into maintained code. It strengthens the case for external specifications, hard resource limits, independent verification, qualitative code review, and human escalation. It does not establish that every [[software-factories|software-factory]] design fails, because the experiment intentionally allowed the model to choose its own workflow and targeted an unusually ambitious interpreter project.

## Todos

- [ ] evaluate loop engineering [https://github.com/fltman/loop-engineer](https://github.com/fltman/loop-engineer) - assess whether [[loop-engineering]] is a practical next step for AI development workflows, starting from [[fltman-loop-engineer]], [[loop-engineer]], and [[agent-loop-guardrails]].
- [ ] evaluate spec-only libraries [https://www.dbreunig.com/2026/01/08/a-software-library-with-no-code.html](https://www.dbreunig.com/2026/01/08/a-software-library-with-no-code.html) - assess whether [[spec-only-libraries]] are useful for small internal utilities and how they affect the spec-driven AI development opinion.
- [ ] evaluate Stack Overflow for Agents [https://stackoverflow.blog/2026/06/10/announcing-stack-overflow-for-agents](https://stackoverflow.blog/2026/06/10/announcing-stack-overflow-for-agents) - assess whether [[agent-knowledge-sharing]] and [[verification-driven-agent-knowledge]] should become part of the AI developer tools thesis.
- [ ] evaluate proposer/verifier/curator loops [https://blog.apiad.net/p/ai-is-doing-something-weird-to-science](https://blog.apiad.net/p/ai-is-doing-something-weird-to-science) - assess whether [[proposer-verifier-curator-loop]] and [[verifier-bottleneck]] should sharpen the loop-engineering opinion.
- [ ] evaluate local agent inference [https://github.com/magnitudedev/magnitude](https://github.com/magnitudedev/magnitude) - assess when [[local-agent-inference]] meaningfully improves privacy, cost, and autonomy for AI developer tools compared with hosted models and cloud sandboxes.
- [ ] evaluate AI-assisted code search [https://moderne.ai/blog/ai-code-search-at-scale-finding-method-invocations-with-natural-language](https://moderne.ai/blog/ai-code-search-at-scale-finding-method-invocations-with-natural-language) - assess whether [[semantic-code-search]] plus [[type-aware-code-search]] is a reliable pattern for AI developer tools.
- [ ] evaluate browser-local sandboxes for AI-assisted web development [https://ma.tt/2026/03/wordpress-everywhere/](https://ma.tt/2026/03/wordpress-everywhere/) - assess whether [[wordpress-playground]] and [[browser-local-software]] meaningfully improve AI-assisted experimentation safety.
- [ ] evaluate governed AI software factories [https://lucumr.pocoo.org/2026/9/7/astra-why/](https://lucumr.pocoo.org/2026/9/7/astra-why/) - compare Ronacher's autonomy-heavy failure case with factory designs that use externally defined stages, independent gates, and bounded work units.
