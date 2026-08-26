---
type: source
tags: [security, tls, web-scanning, python]
updated: 2026-08-26
source_url: https://github.com/nabla-c0d3/sslyze
license: AGPL-3.0
---

# nabla-c0d3/SSLyze

Source: [GitHub repository](https://github.com/nabla-c0d3/sslyze). Raw capture: [raw/nabla-c0d3-sslyze.md](../../raw/nabla-c0d3-sslyze.md).

## Summary

`nabla-c0d3/SSLyze` is the repository for [[sslyze]], a fast SSL/TLS scanning CLI and Python library. It analyzes a server's TLS configuration by connecting to it and checking certificates, cipher suites, elliptic curves, supported protocol behavior, and known TLS vulnerabilities.

This source belongs next to [[whatweb]], but it covers a different layer. WhatWeb fingerprints visible web technologies; SSLyze focuses on [[tls-configuration-scanning]] and [[tls-compliance-in-ci]].

## Key Takeaways

- SSLyze is both a CLI tool and a Python library.
- It checks certificates, cipher suites, elliptic curves, and known TLS attack exposure.
- Known attack checks mentioned by the README include Heartbleed, ROBOT, and OpenSSL CCS injection.
- It supports non-HTTP services including SMTP, XMPP, LDAP, POP, IMAP, RDP, Postgres, and FTP.
- Results can be exported to JSON for later processing.
- The README emphasizes operational use in CI/CD.
- By default, SSLyze checks results against Mozilla's "intermediate" TLS configuration and returns a non-zero exit code if the target is non-compliant.
- The Mozilla profile can be changed with `--mozilla_config={old, intermediate, modern}`.
- Custom TLS profiles can be checked with `--custom_tls_config`.
- The repository includes a Dockerfile; for security-sensitive usage, audit and build locally rather than blindly running a prebuilt image.

## Practical Commands

Install and scan:

```sh
pip install --upgrade sslyze
python -m sslyze www.example.com
```

Mozilla modern profile check:

```sh
python -m sslyze --mozilla_config=modern www.example.com
```

Local container build after reviewing the repository Dockerfile:

```sh
git clone https://github.com/nabla-c0d3/sslyze.git
cd sslyze
docker build -t local/sslyze .
docker run --rm -it local/sslyze www.example.com
```

Use TLS scans only on systems you own or have permission to assess.

## Connections

- [[sslyze]] - central tool.
- [[tls-configuration-scanning]] - core scan category.
- [[tls-compliance-in-ci]] - operational pattern emphasized by the README.
- [[web-technology-fingerprinting]] - adjacent reconnaissance category covered by WhatWeb.

## Follow-ups

- [ ] [SSLyze Python API docs](https://nabla-c0d3.github.io/sslyze/documentation/) - capture embedding scans in Python applications and automation.
- [ ] [SSLyze releases](https://github.com/nabla-c0d3/sslyze/releases) - track version changes, supported Python versions, and trust-store updates.
- [ ] [Mozilla TLS configuration generator](https://ssl-config.mozilla.org/) - capture the policy profiles SSLyze uses for compliance checks.
