---
type: concept
tags: [security, web-scanning, reconnaissance]
updated: 2026-08-26
---

# Web Technology Fingerprinting

Web technology fingerprinting is the process of identifying the software, frameworks, libraries, servers, CMSs, analytics tools, and other components behind a website by observing HTTP responses, page content, headers, paths, assets, errors, and other cues.

The [[urbanadventurer-whatweb]] source presents [[whatweb]] as a dedicated fingerprinting scanner with more than 1800 plugins. It can operate quickly with minimal requests or more aggressively when higher confidence is needed.

In a broader [[external-web-security-scanning]] workflow, web technology fingerprinting pairs naturally with [[tls-configuration-scanning]]: one identifies the visible application stack, while the other checks the encrypted transport posture.

## Defensive Uses

- Build an inventory of exposed web technologies.
- Detect accidental version disclosure.
- Find legacy CMSs, plugins, frameworks, or libraries.
- Compare externally visible technology signals against the expected stack.
- Feed follow-up patching or hardening work.

## Related Pages

- [[whatweb]]
- [[sslyze]]
- [[external-web-security-scanning]]
- [[tls-configuration-scanning]]
- [[outdated-software-exposure]]
