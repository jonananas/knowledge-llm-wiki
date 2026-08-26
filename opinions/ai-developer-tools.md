# AI Developer Tools

Updated: 2026-08-26

This page tracks working opinions about AI developer tools. These are not treated as established conclusions unless supported by cited source pages.

## Current Opinions

- Spec-driven AI development is more structured and probably more successful than just prompting.
- [[loop-engineering]] is possibly the next step after spec-driven AI development; evaluation needed.

## Current Evidence Status

The vault currently has source-backed notes on adjacent tools and concepts: [[fltman-loop-engineer]], [[loop-engineering]], [[agent-loop-guardrails]], [[stack-overflow-for-agents]], [[agent-knowledge-sharing]], [[verification-driven-agent-knowledge]], [[proposer-verifier-curator-loop]], [[verifier-bottleneck]], [[codesandbox]], [[sandboxed-code-execution]], [[fumadocs]], and [[uv]].

It does not yet contain enough comparative evidence to support the claim that spec-driven AI development is more successful than prompting, or that loop engineering is the next step. Treat both as hypotheses.

The [[announcing-stack-overflow-for-agents]] source is relevant but still indirect: it supports the need for verification, shared knowledge, and human-reviewed agent outputs, not the stronger claim that a particular development workflow is superior.

The [[ai-is-doing-something-weird-to-science]] source is also indirect but useful for the loop-engineering hypothesis: it argues that AI value depends less on raw model output and more on the surrounding proposer/verifier/curator loop.

## Todos

- [ ] evaluate loop engineering [https://github.com/fltman/loop-engineer](https://github.com/fltman/loop-engineer) - assess whether [[loop-engineering]] is a practical next step for AI development workflows, starting from [[fltman-loop-engineer]], [[loop-engineer]], and [[agent-loop-guardrails]].
- [ ] evaluate Stack Overflow for Agents [https://stackoverflow.blog/2026/06/10/announcing-stack-overflow-for-agents](https://stackoverflow.blog/2026/06/10/announcing-stack-overflow-for-agents) - assess whether [[agent-knowledge-sharing]] and [[verification-driven-agent-knowledge]] should become part of the AI developer tools thesis.
- [ ] evaluate proposer/verifier/curator loops [https://blog.apiad.net/p/ai-is-doing-something-weird-to-science](https://blog.apiad.net/p/ai-is-doing-something-weird-to-science) - assess whether [[proposer-verifier-curator-loop]] and [[verifier-bottleneck]] should sharpen the loop-engineering opinion.
