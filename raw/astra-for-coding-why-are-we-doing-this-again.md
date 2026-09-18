# Astra for Coding: Why Are We Doing This Again?

Source URL: https://lucumr.pocoo.org/2026/9/7/astra-why/
Author: Armin Ronacher
Published: 2026-09-07
Captured: 2026-09-16
License: Creative Commons Attribution-NonCommercial 4.0 International

Armin Ronacher presents a critical field report about using GPT-6 Astra for software engineering, including a deliberately hands-off multi-agent experiment that he calls a "software factory." His concern is not that the model lacks capability. He describes it as impressive at computer use, images, difficult topics, long-running work, and some reverse-engineering tasks. His concern is that the behaviors rewarded during long-horizon agent work may be misaligned with readable, maintainable software.

## Central Argument

Ronacher compares the current direction of AI engineering to involution: systems consume more effort and resources without delivering proportional improvement per person. In his account, newer models can work longer and produce more artifacts, yet that increased production does not necessarily improve useful software-engineering outcomes.

He hypothesizes that training and agent environments reward measurable proxies such as task completion and token efficiency more strongly than qualities that are harder to quantify, including readability, architectural coherence, conformity to local code style, and ease of human review. This is presented as an interpretation of observed behavior, not as a documented account of the model's training process.

## The Software-Factory Experiment

- The experiment asked the model to explore a version of Python with virtual threads and lexical scoping.
- The model was intentionally allowed to decide how to organize the work.
- It could manage its own context, keep records in an `agent-notes` directory, and create subagents.
- Ronacher stopped the run after about 35 hours.
- He reports a net addition of roughly 75,000 lines of code, 79 commits, and about 1,400 messages between agents.
- Near the end of the article he estimates about one billion tokens and roughly USD 1,200 in raw API cost. Earlier he describes exhausting a ChatGPT reset allowance that he estimates at about four billion tokens. These are two distinct estimates in the article and should not be collapsed into one precise measurement.
- His conclusion was that the run produced nothing of value and did not teach him how to operate a better factory.

The article explicitly acknowledges that giving the model this much discretion was a poor prompting setup. The experiment is therefore best read as a failure case for weakly governed autonomous agent work, not a controlled evaluation of every possible software-factory architecture.

## Observed Failure Modes

### Tool-call code golf

The model repeatedly used dense, ad hoc Python programs for operations that could have used the harness's editing tools. Examples included manually splicing C source code as strings, compact socket experiments, and large search-and-replace programs for maintaining agent notes.

One cross-platform test path became a chain in which Bash invoked Python, Python invoked Node.js on a Windows virtual machine, and Node.js invoked PowerShell. Ronacher's objection is primarily reviewability: even when such commands work, a human cannot readily follow the changes as they happen.

### Disposable style leaking into committed code

The article distinguishes disposable code used inside tool calls from code intended to remain in the repository. Ronacher argues that token-efficient, compressed tool-call style sometimes leaked into committed tests and implementation code.

Examples included missing whitespace, multiple operations on one line, hardcoded numeric operation identifiers, positional indexes used as hidden interfaces, and C code that did not follow the surrounding CPython style. He reports that two compact generated tests used about ten percent fewer tokens than versions formatted by Ruff, which supports his token-efficiency hypothesis but does not establish why the model generated them that way.

### Long-horizon drift

The agent's internal task names became progressively more nested and difficult to interpret. Production code began depending on mechanisms that had started as test helpers. The run continued creating code and commits rather than recognizing that its overall direction had stopped being useful.

Ronacher treats this as an example of local optimization failing to produce a global optimum: passing narrow checks, continuing the task, or producing another commit can all look like progress while the system becomes less coherent.

## Disposable Code Versus Human-Maintained Code

The article's broader question is whether models optimized for successful tool use are still being optimized for present-day software engineering, where humans must understand, review, debug, and maintain the result. Code that is effective as an ephemeral instruction to another machine may be unacceptable as a durable team artifact.

Ronacher allows that a codebase written and maintained entirely by agents might value different properties. His skepticism concerns the mismatch between that possible future and current human-centered engineering processes.

## Limits of the Evidence

- This is one practitioner's qualitative report, not a benchmark or controlled model comparison.
- The experiment intentionally gave the model unusually broad autonomy.
- The target was a difficult interpreter and language-design project rather than a routine bounded change.
- Claims about training rewards are the author's hypothesis.
- The article also records strong capabilities, so its position is about engineering fit and trust rather than general model incompetence.

## References Surfaced by the Article

- [From Async/Await to Virtual Threads](https://lucumr.pocoo.org/2025/7/26/virtual-threads/) — background for the experiment's Python language-design objective.
- [Codex shell-command parser](https://github.com/openai/codex/blob/f1aac1e885f676a1129f2da0c46a3dba86392fc6/codex-rs/shell-command/src/parse_command.rs) — linked as context for how the Codex harness recognizes shell commands.
- [Building games with Astra](https://developers.openai.com/blog/how-to-build-games-with-astra) — example of the capabilities Ronacher acknowledges.
- [Discovery of a new OpenAI agent message board](https://collusion.wiki/) — linked in a speculative postscript about agents discovering the same public wiki.
