---
type: concept
tags: [security, tls, web-scanning]
updated: 2026-08-26
---

# TLS Configuration Scanning

TLS configuration scanning is the practice of connecting to a server and checking its supported TLS versions, certificates, cipher suites, elliptic curves, extensions, and exposure to known TLS vulnerabilities.

The [[nabla-c0d3-sslyze]] source positions [[sslyze]] as a tool for this job. Unlike [[web-technology-fingerprinting]], which identifies web stack technologies, TLS scanning focuses on whether the encrypted transport layer is configured safely. In [[external-web-security-scanning]], the two checks are complementary.

## What To Check

- Certificate chain validity and certificate characteristics.
- Supported TLS protocol versions.
- Cipher suites and key exchange behavior.
- Elliptic curve support.
- Known TLS attack exposure, such as Heartbleed, ROBOT, and OpenSSL CCS injection.
- Compliance with policy profiles such as Mozilla old/intermediate/modern.

## Operational Use

TLS scans are useful in asset inventory, release checks, migration work, and periodic security monitoring. Results should be interpreted against the system's audience and compatibility requirements, because strict "modern" TLS settings may intentionally reject older clients. [[nabla-c0d3-sslyze]]

Use TLS scans only on systems you own or have permission to assess.

## Related Pages

- [[sslyze]]
- [[whatweb]]
- [[external-web-security-scanning]]
- [[tls-compliance-in-ci]]
- [[web-technology-fingerprinting]]
