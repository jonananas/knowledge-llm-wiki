---
type: entity
tags: [security, web-scanning, reconnaissance, ruby]
updated: 2026-08-26
---

# WhatWeb

WhatWeb is a web scanner for identifying technologies used by websites. Its README says it recognizes CMSs, blogging platforms, analytics packages, JavaScript libraries, web servers, embedded devices, version numbers, email addresses, account IDs, web framework modules, SQL errors, and more. [[urbanadventurer-whatweb]]

## Role

WhatWeb is useful for web reconnaissance and defensive asset inventory. It can reveal exposed software stacks and version information that should be reviewed for patching, removal, or reduced fingerprintability.

## Outdated Software

Run `whatweb -v -a 3 yourdomain.com` against any website. Every outdated CMS version, plugin, library, or framework version it reveals is a potential known vulnerability waiting to be exploited.

Use this kind of scan only on domains and systems you own or have permission to assess.

## Aggression Levels

- `-a 1`: stealthy default mode, one HTTP request per website.
- `-a 3`: aggressive mode, additional requests are made if a level 1 plugin matches.
- `-a 4`: heavy mode, aggressive tests from all plugins are used for all URLs.

## Related Pages

- [[web-technology-fingerprinting]]
- [[outdated-software-exposure]]

## Follow-ups

- [ ] [WhatWeb wiki](https://github.com/urbanadventurer/WhatWeb/wiki/) - preserve practical installation and scanning guidance.
- [ ] [WhatWeb plugin development docs](https://github.com/urbanadventurer/WhatWeb/tree/master/plugin-development) - capture how custom fingerprints are written.
