# fltman/loop-engineer

Source URL: https://github.com/fltman/loop-engineer
Primary source viewed: repository README
License: MIT
Captured: 2026-08-26

`fltman/loop-engineer` is a GitHub repository containing a Claude Code skill and related subagents for setting up and administering guarded agentic loops. It frames "loop engineering" as a shift from focusing on source code, to focusing on an agent, to focusing on the loop that prompts and controls the agent.

## Main Points

- The repository packages a `loop-engineer` skill, a `loop-architect` subagent, a `loop-teacher` subagent, and slash-command shortcuts.
- It assumes Claude Code already provides loop primitives such as `claude -p`, `/loop`, `/goal`, Tasks, and cloud Routines.
- The project focuses on choosing, scaffolding, and guarding loops rather than inventing the low-level loop primitives.
- The core failure mode it is designed to prevent is an unbounded or vague loop that keeps running and spending money without converging.
- The repo includes a skill knowledge pack with a decision tree, primitive reference, taxonomy reference, guardrails reference, and runnable templates.
- Templates include a headless loop around `claude -p`, an evaluator-optimizer loop, a meta prompt-refinement loop, an orchestrator fan-out loop, and a `/goal`/`/loop` recipe.
- The slash-command shortcuts are `/new-loop`, `/loop-audit`, and `/learn-loops`; the names avoid colliding with Claude Code's built-in `/loop`.
- The five loop patterns are headless while-loop, evaluator-optimizer, meta or prompt-refinement, orchestrator fan-out, and scheduled or triggered loops.
- The repository's central rule is that a loop needs a binary, verifiable exit condition before it should run.
- The five mandatory guardrails are: verifiable exit condition, hard max-iteration cap, budget cap in code, sandboxed working environment, and human checkpoint for irreversible actions.
- Installation is by copying the `.claude/skills/loop-engineer` and `.claude/agents/loop-architect.md` content into a project `.claude/` directory or the user's global `~/.claude/` directory.
- The README warns that the template parsing of `claude -p --output-format json` should be verified against the user's installed Claude Code version before unattended use.

## Loop Patterns

- Headless while-loop: one agent working against one binary check.
- Evaluator-optimizer: a generator paired with a separate critic for quality judgments.
- Meta or prompt-refinement: a loop that improves the prompt used by another loop.
- Orchestrator fan-out: an orchestrator that assigns unpredictable subtasks to workers and verifies outputs.
- Scheduled or triggered: interval, self-paced, or cloud-routine execution.

## Provenance Claimed By The Repo

The README says the taxonomy draws from Anthropic's "Building Effective Agents", the meta-loop lineage from "Self-Taught Evaluators", and shell fan-out/headless-CI loops from community patterns rather than official Anthropic endorsements.

## Notable Links From The Repo

- Repository: https://github.com/fltman/loop-engineer
- Anthropic Building Effective Agents: https://www.anthropic.com/engineering/building-effective-agents
- Self-Taught Evaluators paper: https://arxiv.org/abs/2408.02666
