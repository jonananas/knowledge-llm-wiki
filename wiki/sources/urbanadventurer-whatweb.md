---
type: source
tags: [security, web-scanning, reconnaissance, developer-tools]
updated: 2026-08-26
source_url: https://github.com/urbanadventurer/whatweb
license: GPLv2
---

# urbanadventurer/WhatWeb

Source: [GitHub repository](https://github.com/urbanadventurer/whatweb). Raw capture: [raw/urbanadventurer-whatweb.md](../../raw/urbanadventurer-whatweb.md).

## Summary

`urbanadventurer/WhatWeb` is the GitHub repository for [[whatweb]], a web technology fingerprinting scanner. The README describes WhatWeb as a tool for answering what technologies power a website: CMSs, blogging platforms, analytics packages, JavaScript libraries, web servers, embedded devices, and related components.

The source is relevant for [[web-technology-fingerprinting]] and [[outdated-software-exposure]] because WhatWeb can identify version numbers and other technology cues that may reveal stale or vulnerable software.

## Key Takeaways

- WhatWeb recognizes website technologies through more than 1800 plugins.
- It can identify version numbers, email addresses, account IDs, web framework modules, SQL errors, and more.
- Its aggression levels control the tradeoff between speed, stealth, reliability, and thoroughness.
- Default aggression level `1` is stealthy and uses one HTTP request per website.
- Aggression level `3` makes additional requests when a level 1 plugin matches.
- Aggression level `4` applies aggressive tests from all plugins to all URLs.
- The README frames stealthy mode as suitable for scanning public websites and more aggressive modes as designed for penetration tests.
- Output formats include brief, verbose, XML, JSON, MagicTree, RubyObject, MongoDB, ElasticSearch, and SQL.

## Outdated Software

Run `whatweb -v -a 3 yourdomain.com` against any website. Every outdated CMS version, plugin, library, or framework version it reveals is a potential known vulnerability waiting to be exploited.

Use this kind of scan only on domains and systems you own or have permission to assess.

## Connections

- [[whatweb]] - central tool.
- [[web-technology-fingerprinting]] - category of detection WhatWeb performs.
- [[outdated-software-exposure]] - risk surfaced by version and component detection.

## Follow-ups

- [ ] [WhatWeb wiki](https://github.com/urbanadventurer/WhatWeb/wiki/) - capture installation, plugin usage, and operational guidance.
- [ ] [WhatWeb plugins directory](https://github.com/urbanadventurer/WhatWeb/tree/master/plugins) - understand what technologies are detectable and how signatures are implemented.
- [ ] [WhatWeb changelog](https://github.com/urbanadventurer/WhatWeb/blob/master/CHANGELOG.md) - track release history and plugin coverage changes.
