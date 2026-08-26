---
type: concept
tags: [security, vulnerability-management, web-scanning]
updated: 2026-08-26
---

# Outdated Software Exposure

Outdated software exposure is the risk created when a website reveals old CMS versions, plugins, libraries, frameworks, web servers, or other components that may have known vulnerabilities.

The [[urbanadventurer-whatweb]] source matters because [[whatweb]] can identify version numbers and technology cues. Those findings can become a first-pass list of components to patch, replace, hide, or verify against vulnerability databases.

## Practical Note

Run `whatweb -v -a 3 yourdomain.com` against any website. Every outdated CMS version, plugin, library, or framework version it reveals is a potential known vulnerability waiting to be exploited.

If containerizing WhatWeb, the `ilyaglow/dockerfiles` repo has an example Dockerfile under `whatweb/` that can be reviewed and built locally. Avoid treating third-party prebuilt images as trusted by default. [[ilyaglow-dockerfiles-whatweb]]

```sh
docker run -it --rm local/whatweb -v -a 3 yourdomain.com
```

Use this kind of scan only on domains and systems you own or have permission to assess.

## Related Pages

- [[whatweb]]
- [[web-technology-fingerprinting]]
- [[ilyaglow-dockerfiles-whatweb]]
