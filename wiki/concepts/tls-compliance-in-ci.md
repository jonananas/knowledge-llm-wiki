---
type: concept
tags: [security, tls, ci-cd, devsecops]
updated: 2026-08-26
---

# TLS Compliance In CI

TLS compliance in CI is the practice of running automated TLS checks as part of a build, deployment, or scheduled monitoring workflow so weak server-side encryption settings fail fast.

The [[nabla-c0d3-sslyze]] source explicitly supports this pattern: SSLyze checks scan results against Mozilla's recommended TLS configurations and returns a non-zero exit code when a target is not compliant.

## Common Policy Inputs

- Mozilla "old" profile for legacy compatibility.
- Mozilla "intermediate" profile as the default balanced recommendation.
- Mozilla "modern" profile for stricter clients and deployments.
- Custom TLS configuration JSON for organization-specific policy.

## Why It Matters

TLS configuration can regress during infrastructure changes, certificate replacement, load balancer changes, or platform migrations. A CI or scheduled check turns TLS posture into a repeatable policy test instead of a one-off audit.

## Related Pages

- [[sslyze]]
- [[tls-configuration-scanning]]
