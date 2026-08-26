# Web Tools

Updated: 2026-08-26

This page tracks working opinions about practical web tooling. These are not treated as established conclusions unless supported by cited source pages.

## Current Opinionated best practices

- Scanning websites regularly for TLS configuration flaws, e.g. with [[sslyze]]
- Scanning websites regularly for exposed software stacks, e.g. with [[whatweb]]
- Use [[pnpm]] as package manager for JavaScript projects. It is fast, secure, and has wide support. [[bun]] is faster in some scenarios, but is missing security and wide support among other maturity concerns.

## Current Evidence Status

The vault currently has source-backed notes on [[whatweb]], [[urbanadventurer-whatweb]], [[ilyaglow-dockerfiles-whatweb]], [[sslyze]], [[nabla-c0d3-sslyze]], [[web-technology-fingerprinting]], [[tls-configuration-scanning]], [[outdated-software-exposure]], [[tls-compliance-in-ci]], [[external-web-security-scanning]], [[pnpm-vs-npm-vs-yarn-vs-bun-2026]], [[javascript-package-management]], [[javascript-package-manager-selection]], [[javascript-monorepo-package-management]], [[pnpm]], and [[bun]].

The evidence supports the basic complementarity of WhatWeb and SSLyze, but the vault does not yet contain a tested, opinionated baseline checklist for web security scans. Treat the workflow as a hypothesis until evaluated on owned systems.

The evidence supports pnpm as a strong default candidate, especially around performance, disk efficiency, monorepo support, compatibility, and production-oriented security workflows. It also supports the Bun caveat: Bun is faster in the cited benchmarks, but the source notes missing built-in security auditing and remaining compatibility concerns.

## Todos

- [ ] evaluate a baseline external web security scan using [[whatweb]] plus [[sslyze]] on owned domains.
- [ ] decide whether the baseline should use direct local installs, locally built containers, or both.
- [ ] define default TLS policy: Mozilla intermediate versus modern, plus any custom profile requirements.
- [ ] decide where recurring checks belong: local script, CI/CD, scheduled monitoring, or all three.
- [ ] verify current pnpm security, workspace, and lockfile behavior from first-party docs.
- [ ] verify current Bun audit, lockfile, and npm compatibility behavior from first-party docs.
- [ ] test pnpm as the default package manager on an owned project.
- [ ] define when Bun is acceptable despite the default pnpm recommendation.
