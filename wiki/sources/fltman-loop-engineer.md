---
type: source
tags: [ai-agents, claude-code, developer-tools, automation]
updated: 2026-08-26
source_url: https://github.com/fltman/loop-engineer
license: MIT
---

# fltman/loop-engineer

Source: [GitHub repository](https://github.com/fltman/loop-engineer). Raw capture: [raw/fltman-loop-engineer.md](../../raw/fltman-loop-engineer.md).

## Summary

`fltman/loop-engineer` packages [[loop-engineer]] as a [[claude-code]] skill plus subagents for designing, scaffolding, teaching, and auditing [[loop-engineering]] workflows. The README frames loop engineering as the next abstraction level after prompting: the developer designs the system that repeatedly prompts and checks the agent.

The repo's practical contribution is a taxonomy of loop patterns plus strict [[agent-loop-guardrails]]. It does not primarily introduce a new runtime. Instead, it assumes Claude Code already has primitives such as `claude -p`, `/loop`, `/goal`, Tasks, and cloud Routines, then adds decision support, templates, and guardrails around them.

## Key Takeaways

- The tool is designed for agentic loops that may run more than one iteration without the developer typing each next prompt.
- Its core rule is that no loop should run without a binary, verifiable exit condition.
- It ships templates for five patterns: headless while-loop, evaluator-optimizer, meta or prompt-refinement, orchestrator fan-out, and scheduled or triggered loops.
- The repo includes a `loop-architect` subagent for interactive loop design and a `loop-teacher` subagent for explaining the mental model.
- Slash commands include `/new-loop`, `/loop-audit`, and `/learn-loops`; these avoid colliding with Claude Code's built-in `/loop`.
- The guardrail checklist is explicit: verifiable exit condition, hard max-iteration cap, budget cap in code, sandboxed work environment, and human checkpoint for irreversible actions.
- The README warns users to verify `claude -p --output-format json` fields against their installed Claude Code version before unattended runs.

## Connections

- [[loop-engineer]] - the repository/tool entity.
- [[claude-code]] - host environment and primitive provider according to the repo.
- [[loop-engineering]] - discipline the repo is packaging.
- [[agent-loop-guardrails]] - safety and cost-control checklist.
- [[sandboxed-code-execution]] - related isolation concern, especially for unattended loops.

## Follow-ups

- [ ] [Anthropic Building Effective Agents](https://www.anthropic.com/engineering/building-effective-agents) - ingest the stated source for the architecture taxonomy.
- [ ] [Self-Taught Evaluators](https://arxiv.org/abs/2408.02666) - ingest the stated source for the meta-loop lineage.
- [ ] [Claude Code docs](https://docs.anthropic.com/en/docs/claude-code) - verify the current status and semantics of `claude -p`, `/loop`, `/goal`, Tasks, and cloud Routines.
