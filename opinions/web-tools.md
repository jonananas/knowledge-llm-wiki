# Web Tools

Updated: 2026-08-26

This page tracks working opinions about practical web tooling. These are not treated as established conclusions unless supported by cited source pages.

## Current Opinionated best practices

- Scanning websites regularly for TLS configuration flaws, e.g. with [[sslyze]]
- Scanning websites regularly for exposed software stacks, e.g. with [[whatweb]]

## Current Evidence Status

The vault currently has source-backed notes on [[whatweb]], [[urbanadventurer-whatweb]], [[ilyaglow-dockerfiles-whatweb]], [[sslyze]], [[nabla-c0d3-sslyze]], [[web-technology-fingerprinting]], [[tls-configuration-scanning]], [[outdated-software-exposure]], [[tls-compliance-in-ci]], and [[external-web-security-scanning]].

The evidence supports the basic complementarity of WhatWeb and SSLyze, but the vault does not yet contain a tested, opinionated baseline checklist for web security scans. Treat the workflow as a hypothesis until evaluated on owned systems.

## Todos

- [ ] evaluate a baseline external web security scan using [[whatweb]] plus [[sslyze]] on owned domains.
- [ ] decide whether the baseline should use direct local installs, locally built containers, or both.
- [ ] define default TLS policy: Mozilla intermediate versus modern, plus any custom profile requirements.
- [ ] decide where recurring checks belong: local script, CI/CD, scheduled monitoring, or all three.
