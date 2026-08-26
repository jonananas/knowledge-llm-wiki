---
type: entity
tags: [security, tls, web-scanning, python]
updated: 2026-08-26
---

# SSLyze

SSLyze is a fast SSL/TLS scanning tool and Python library from `nabla-c0d3/sslyze`. It connects to servers to analyze TLS configuration, including certificates, cipher suites, elliptic curves, and exposure to known TLS attacks such as Heartbleed, ROBOT, and OpenSSL CCS injection. [[nabla-c0d3-sslyze]]

## Role

SSLyze is useful for defensive TLS inventory and compliance checks. It can be used manually, scripted through its Python API, or run as a CI/CD gate to catch weak server-side TLS configurations before or after deployment.

In [[external-web-security-scanning]], SSLyze complements [[whatweb]]: SSLyze covers the transport layer, while WhatWeb identifies visible application technologies, versions, plugins, libraries, frameworks, and other stack signals.

## Operational Notes

- Default checks compare results against Mozilla's "intermediate" TLS profile.
- `--mozilla_config=old|intermediate|modern` selects a Mozilla profile.
- `--custom_tls_config` checks against a custom TLS configuration file using Mozilla's format.
- JSON output makes scan results easier to archive or process automatically.
- Non-HTTP protocol support makes it useful beyond normal HTTPS websites.

## Containerization

The repository includes a Dockerfile. For security-sensitive use, review the Dockerfile and build a local image rather than trusting a prebuilt image by default. [[nabla-c0d3-sslyze]]

```sh
git clone https://github.com/nabla-c0d3/sslyze.git
cd sslyze
docker build -t local/sslyze .
docker run --rm -it local/sslyze www.example.com
```

Use TLS scans only on systems you own or have permission to assess.

## Related Pages

- [[external-web-security-scanning]]
- [[whatweb]]
- [[tls-configuration-scanning]]
- [[tls-compliance-in-ci]]
