---
type: source
tags: [python, packaging, rust, developer-tools]
updated: 2026-08-26
source_url: https://astral.sh/blog/uv
author: Charlie Marsh
published: 2024-02-15
---

# uv: Python packaging in Rust

Source: [Astral blog](https://astral.sh/blog/uv). Raw capture: [raw/astral-uv.md](../../raw/astral-uv.md).

## Summary

Astral's launch post introduces [[uv]] as a Rust-written Python package installer and resolver that can replace `pip`, `pip-tools`, and `virtualenv` in existing workflows. The release is deliberately scoped: `uv` starts with a drop-in `uv pip` interface while laying the foundation for a fuller "Cargo for Python" project manager.

The article also announces that [[astral]] is taking stewardship of [[rye]], treating it as an experimental project-management surface and migration path while `uv` grows into the unified successor.

## Key Takeaways

- `uv` was launched as production-ready for projects already built around `pip` and `pip-tools` workflows.
- The early value proposition is speed plus compatibility: Astral reported 8-10x faster runs than `pip` and `pip-tools` without caching and 80-115x faster runs with a warm cache.
- The `uv pip` namespace preserves the familiar lower-level commands while leaving room for a higher-level project API.
- `uv` ships as a static binary without depending directly on Python, making it easier to install independently from interpreter management.
- The roadmap is broader than package installation: Astral wants `uv` to become a single tool that can eventually cover package management, project management, Python bootstrapping, and related tooling.

## Technical Notes

`uv` uses a global module cache and can use filesystem hardlinks or copy-on-write to reduce repeated downloads, builds, and disk usage. It supports modern dependency sources and install patterns, including editable installs, Git dependencies, URL dependencies, local dependencies, constraint files, source distributions, and custom indexes.

The resolver adds workflows that are hard or awkward with `pip-tools`: resolving against a target Python version, lowest-compatible resolution for library testing, and override files that let users repair bad upstream dependency declarations. The article notes that `uv` includes Rust implementations of several packaging standards, including PEP 440, PEP 508, PEP 517, and PEP 405.

## Caveats

At launch, `uv` was not a complete `pip` replacement for every legacy workflow. Astral explicitly called out missing support for some legacy features such as `.egg` distributions. It also did not yet produce a platform-agnostic lockfile, making it closer to `pip-tools` than Poetry or PDM in that respect.

## Connections

- [[uv]] - central tool announced in the post.
- [[astral]] - company building the toolchain.
- [[rye]] - project Astral took stewardship of as part of the `uv` roadmap.
- [[python-packaging]] - ecosystem problem area the article addresses.
- [[dependency-resolution]] - core technical capability behind the tool.
