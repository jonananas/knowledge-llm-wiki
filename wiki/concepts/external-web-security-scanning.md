---
type: concept
tags: [security, web-scanning, reconnaissance, tls]
updated: 2026-08-26
---

# External Web Security Scanning

External web security scanning is the practice of assessing what a website or internet-facing service exposes from the outside: application technologies, versions, headers, TLS posture, certificates, protocol support, and known weak configurations.

The current vault has two complementary tools in this space:

- [[whatweb]] identifies visible application-layer technologies and version clues through [[web-technology-fingerprinting]].
- [[sslyze]] checks transport-layer encryption through [[tls-configuration-scanning]] and can enforce TLS policy through [[tls-compliance-in-ci]].

## Touching Points

Both tools answer the same defensive question from different layers: what can an external observer learn or exploit from this exposed service?

WhatWeb is strongest for asset fingerprinting and outdated software clues: CMS versions, plugins, JavaScript libraries, frameworks, servers, and other web stack signals. SSLyze is strongest for TLS posture: certificate validation, supported TLS versions, cipher suites, elliptic curves, and known TLS attack exposure.

Together they form a useful first-pass external audit:

```sh
whatweb -v -a 3 yourdomain.com
python -m sslyze --mozilla_config=modern yourdomain.com
```

Use these scans only on domains and systems you own or have permission to assess.

## Workflow

- Use WhatWeb to inventory visible web technologies and exposed version clues.
- Use SSLyze to check whether the TLS endpoint satisfies the intended security profile.
- Treat findings as triage inputs, not final proof of exploitability.
- Prefer auditable local installs or locally built containers over unknown third-party images.
- For repeatable checks, move policy-like tests into CI or scheduled monitoring.

## Related Pages

- [[whatweb]]
- [[sslyze]]
- [[web-technology-fingerprinting]]
- [[tls-configuration-scanning]]
- [[outdated-software-exposure]]
- [[tls-compliance-in-ci]]
