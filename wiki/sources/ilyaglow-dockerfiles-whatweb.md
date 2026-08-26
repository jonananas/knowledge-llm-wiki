---
type: source
tags: [security, docker, whatweb, web-scanning]
updated: 2026-08-26
source_url: https://github.com/ilyaglow/dockerfiles/tree/master
---

# ilyaglow/dockerfiles: WhatWeb Dockerfile

Source: [ilyaglow/dockerfiles](https://github.com/ilyaglow/dockerfiles/tree/master). Raw capture: [raw/ilyaglow-dockerfiles-whatweb.md](../../raw/ilyaglow-dockerfiles-whatweb.md).

## Summary

The `ilyaglow/dockerfiles` repository contains a `whatweb/` directory with an example Dockerfile for running [[whatweb]] through Docker.

This source is a practical addendum to [[urbanadventurer-whatweb]]: it records where to find an example container definition that can be audited, modified, and built locally instead of installing the Ruby toolchain directly on the host.

## Key Takeaways

- Relevant repository path: [whatweb/](https://github.com/ilyaglow/dockerfiles/tree/master/whatweb).
- Treat the repository's Dockerfile as an example to review and build yourself, not as a reason to run a third-party prebuilt image.
- Before relying on it for security work, verify the base image, installed packages, upstream WhatWeb version, and update behavior.

## Dockerfile Usage

Build a local image after reviewing the Dockerfile:

```sh
git clone https://github.com/ilyaglow/dockerfiles.git
cd dockerfiles
docker build -t local/whatweb ./whatweb
```

Containerized version of the outdated-software check:

```sh
docker run -it --rm local/whatweb -v -a 3 yourdomain.com
```

Use this kind of scan only on domains and systems you own or have permission to assess.

## Connections

- [[whatweb]] - scanner being containerized.
- [[web-technology-fingerprinting]] - scan category.
- [[outdated-software-exposure]] - defensive risk surfaced by version detection.
