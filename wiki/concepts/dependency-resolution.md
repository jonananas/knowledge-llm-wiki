---
type: concept
tags: [dependency-management, python, packaging]
updated: 2026-08-26
---

# Dependency Resolution

Dependency resolution is the process of selecting package versions that satisfy a project's declared constraints, transitive dependencies, environment markers, and target runtime requirements.

The [[astral-uv]] source treats resolution as a core technical bottleneck in Python packaging. [[uv]] is notable because it implements a fast resolver in Rust and exposes resolution workflows that are useful beyond basic installation.

## Resolution Modes Highlighted By uv

- Latest-compatible resolution: the default Python packaging behavior, selecting the newest versions that satisfy constraints.
- Lowest-compatible resolution: useful for libraries that want to test against the minimum dependency versions they claim to support.
- Target-version resolution: resolving for a chosen Python version even when running the resolver under a different local Python version.
- Overrides: escape hatches for correcting or bypassing bad upstream dependency metadata.

## Related Pages

- [[uv]]
- [[python-packaging]]
