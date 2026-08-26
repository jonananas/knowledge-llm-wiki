# uv: Python packaging in Rust

Source URL: https://astral.sh/blog/uv
Author: Charlie Marsh
Published: 2024-02-15
Captured: 2026-08-26

Astral announced `uv`, a Rust-written Python package installer and resolver intended to be a fast, production-ready replacement for `pip` and `pip-tools` workflows. The launch framed `uv` as a milestone toward a broader "Cargo for Python": a single, reliable, high-performance toolchain for Python project and package management.

## Main Points

- `uv` initially targets the lower-level `pip` and `pip-tools` surface through commands such as `uv pip install`, `uv pip compile`, `uv pip sync`, and `uv venv`.
- Astral reported launch benchmarks of about 8-10x faster resolution and installation than `pip` and `pip-tools` without caching, and 80-115x faster with a warm cache.
- `uv` uses a global module cache and can use copy-on-write or hardlinks on supported filesystems to reduce downloads, rebuilds, and disk usage.
- The tool ships as a single static binary with no direct Python dependency, so it can be installed independently of any particular Python interpreter.
- It supports common modern packaging cases including editable installs, Git dependencies, URL dependencies, local dependencies, constraints, source distributions, and custom indexes.
- `uv venv` is presented as a much faster virtual environment creator while still producing standards-compliant virtual environments.
- The resolver supports capabilities beyond typical `pip-tools` workflows, including lowest-compatible dependency resolution, resolving for arbitrary target Python versions, and dependency overrides.
- At launch, `uv` did not support every legacy `pip` feature, including `.egg` distributions, and did not generate a platform-agnostic lockfile.
- Astral also announced it was taking stewardship of Rye, with a plan to maintain it, migrate it toward `uv` internals, and eventually provide a smooth migration path to `uv`.

## Strategic Framing

Astral positioned `uv` as both a practical immediate replacement for existing `pip` and `pip-tools` workflows and as infrastructure for a future unified Python toolchain. The article contrasts Python's fragmented tooling experience with Rust's more integrated Cargo-centered workflow, arguing that Python needs tools that feel more reliable and lower-friction.

## Notable Links From The Article

- `uv` repository: https://github.com/astral-sh/uv
- `uv` documentation: https://docs.astral.sh/uv/
- Rye repository: https://github.com/astral-sh/rye
- Cargo: https://github.com/rust-lang/cargo
- PubGrub solver implementation used by `uv`: https://github.com/pubgrub-rs/pubgrub
