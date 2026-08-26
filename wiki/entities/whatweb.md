---
type: entity
tags: [security, web-scanning, reconnaissance, ruby]
updated: 2026-08-26
---

# WhatWeb

WhatWeb is a web scanner for identifying technologies used by websites. Its README says it recognizes CMSs, blogging platforms, analytics packages, JavaScript libraries, web servers, embedded devices, version numbers, email addresses, account IDs, web framework modules, SQL errors, and more. [[urbanadventurer-whatweb]]

## Role

WhatWeb is useful for web reconnaissance and defensive asset inventory. It can reveal exposed software stacks and version information that should be reviewed for patching, removal, or reduced fingerprintability.

In [[external-web-security-scanning]], WhatWeb complements [[sslyze]]: WhatWeb covers application-layer technology and version fingerprints, while SSLyze covers TLS certificates, protocols, ciphers, curves, and known transport-layer weaknesses.

## Outdated Software

Run `whatweb -v -a 3 yourdomain.com` against any website. Every outdated CMS version, plugin, library, or framework version it reveals is a potential known vulnerability waiting to be exploited.

Use this kind of scan only on domains and systems you own or have permission to assess.

## Docker Usage

The `ilyaglow/dockerfiles` repository contains a `whatweb/` Dockerfile directory that can be used as an example for building your own WhatWeb container. Treat it as a starting point to audit and update locally rather than running a third-party prebuilt image directly. [[ilyaglow-dockerfiles-whatweb]]

Example local build flow:

```sh
git clone https://github.com/ilyaglow/dockerfiles.git
cd dockerfiles
docker build -t local/whatweb ./whatweb
```

Containerized equivalent of the outdated-software check:

```sh
docker run -it --rm local/whatweb -v -a 3 yourdomain.com
```

Before relying on a containerized scanner for security work, verify the Dockerfile's base image, package versions, upstream WhatWeb version, and update behavior. [[ilyaglow-dockerfiles-whatweb]]

## Aggression Levels

- `-a 1`: stealthy default mode, one HTTP request per website.
- `-a 3`: aggressive mode, additional requests are made if a level 1 plugin matches.
- `-a 4`: heavy mode, aggressive tests from all plugins are used for all URLs.

## Related Pages

- [[external-web-security-scanning]]
- [[sslyze]]
- [[web-technology-fingerprinting]]
- [[outdated-software-exposure]]
- [[ilyaglow-dockerfiles-whatweb]]

## Follow-ups

- [ ] [WhatWeb wiki](https://github.com/urbanadventurer/WhatWeb/wiki/) - preserve practical installation and scanning guidance.
- [ ] [WhatWeb plugin development docs](https://github.com/urbanadventurer/WhatWeb/tree/master/plugin-development) - capture how custom fingerprints are written.
