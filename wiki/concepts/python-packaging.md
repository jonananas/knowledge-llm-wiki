---
type: concept
tags: [python, packaging, developer-tools]
updated: 2026-08-26
---

# Python Packaging

Python packaging covers the tools and standards used to describe dependencies, resolve compatible package versions, build distributions, install packages, create virtual environments, and manage project workflows.

The [[astral-uv]] source frames Python packaging as a fragmented, low-confidence experience compared with Rust's Cargo-centered tooling. [[uv]] is presented as a consolidation effort: first replacing `pip`, `pip-tools`, and `virtualenv` workflows, then growing toward a more complete project and package manager.

## Tooling Surface

The article identifies several parts of the packaging toolchain that often live in separate tools:

- Package installation: commonly `pip`.
- Requirements locking and syncing: commonly `pip-tools`.
- Virtual environment creation: commonly `venv` or `virtualenv`.
- Project and package management: tools such as Poetry, PDM, and Rye.
- Interpreter and tool bootstrapping: adjacent tools such as `pyenv`, `pipx`, and `tox`.

## Standards Mentioned

The `uv` launch post emphasizes standards-compliant implementations as part of its legitimacy as replacement infrastructure. It mentions PEP 440 for version identifiers, PEP 508 for dependency specifiers, PEP 517 for build-system interfaces, and PEP 405 for virtual environments. [[astral-uv]]

## Related Pages

- [[uv]]
- [[dependency-resolution]]
- [[rye]]
