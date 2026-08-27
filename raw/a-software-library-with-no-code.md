# A Software Library with No Code

Source URL: https://www.dbreunig.com/2026/01/08/a-software-library-with-no-code.html
Author: Drew Breunig
Published: 2026-01-08
Captured: 2026-08-26

Drew Breunig introduces `whenwords`, a relative time formatting library that ships no implementation code. Instead, it ships a specification, language-agnostic tests, and installation instructions that ask a coding agent to generate an implementation in the user's target language and location.

## Main Points

- `whenwords` converts between timestamps, durations, and human-readable strings.
- It provides five functions: `timeago`, `duration`, `parse_duration`, `human_date`, and `date_range`.
- The project is intentionally language-agnostic and was tried in Ruby, Python, Rust, Elixir, Swift, PHP, Bash, and Excel formulas.
- Instead of library code, `whenwords` includes `SPEC.md`, `tests.yaml`, and `INSTALL.md`.
- `SPEC.md` defines behavior and implementation expectations.
- `tests.yaml` defines language-agnostic input/output tests that any generated implementation must pass.
- `INSTALL.md` instructs the human to ask a coding agent such as Claude, Codex, Cursor, or another coding tool to read the spec, generate tests, implement the functions, run tests, and place the implementation where requested.
- The article treats `whenwords` as a thought experiment for what software engineering looks like when coding is cheap.
- Breunig argues the model may make sense for simple utility libraries with stable behavior, few dependencies, non-critical performance, and compact specs.
- He lists five reasons conventional code libraries still matter: performance, complicated testing, support and bug fixes, continual updates, and community/interoperability.
- The article warns that spec-only libraries create support and reproducibility problems because different agents, languages, and runs can produce different implementations.
- The article distinguishes implement-and-forget utilities from foundational dependencies such as databases, frameworks, servers, and security-relevant libraries.
- It concludes that open-source code is also community, bug history, interoperability, test culture, and maintained reference behavior, not just an instantiation of a specification.

## Strategic Framing

The source is useful for thinking about spec-driven AI development. Its strongest claim is not that libraries without code should replace normal libraries. It is that capable coding agents make it plausible to distribute small utilities as precise specs plus tests, then synthesize idiomatic code at the edge of use.

## Notable Links

- whenwords repository: https://github.com/dbreunig/whenwords
- whenwords SPEC.md: https://github.com/dbreunig/whenwords/blob/main/SPEC.md
- whenwords INSTALL.md: https://github.com/dbreunig/whenwords/blob/main/INSTALL.md
- LiteLLM example mentioned in the article: https://www.litellm.ai/
