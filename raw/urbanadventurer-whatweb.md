# urbanadventurer/WhatWeb

Source URL: https://github.com/urbanadventurer/whatweb
Primary source viewed: repository README
Latest release noted by README: v0.6.4, 2026-04-03
License: GPLv2
Captured: 2026-08-26

Run `whatweb -v -a 3 yourdomain.com` against any website. Every outdated CMS version, plugin, library, or framework version it reveals is a potential known vulnerability waiting to be exploited.

WhatWeb is a web scanner for identifying technologies used by websites. Its README describes the goal as answering "What is that Website?" by recognizing content management systems, blogging platforms, analytics packages, JavaScript libraries, web servers, embedded devices, and related web technologies.

## Main Points

- WhatWeb was developed by Andrew Horton and Brendan Coles.
- The README calls it a "next generation web scanner".
- It recognizes website technologies using more than 1800 plugins.
- It can identify version numbers, email addresses, account IDs, web framework modules, SQL errors, and more.
- It supports different aggression levels that trade speed and stealth for reliability and thoroughness.
- The default aggression level is `1`, called stealthy; it is the fastest and uses one HTTP request per website.
- Aggression level `3` is aggressive: if a level 1 plugin is matched, additional requests are made.
- Aggression level `4` is heavy: aggressive tests from all plugins are used for all URLs.
- The README says stealthy mode is suitable for scanning public websites, while more aggressive modes were developed for penetration tests.
- WhatWeb supports multiple log formats including brief, verbose, XML, JSON, MagicTree, RubyObject, MongoDB, ElasticSearch, and SQL.
- It supports proxy usage, including TOR, custom HTTP headers, basic HTTP authentication, redirection controls, IP ranges, fuzzy matching, custom plugins, and plugin search/listing.

## Strategic Use

WhatWeb is useful for initial web reconnaissance and defensive inventory. Its technology and version output can reveal whether a site is exposing legacy CMSs, plugins, frameworks, libraries, or server components that should be patched, hidden, or removed.

## Notable Links From The Repo

- Repository: https://github.com/urbanadventurer/WhatWeb
- Wiki: https://github.com/urbanadventurer/WhatWeb/wiki/
- Project homepage listed in usage output: https://morningstarsecurity.com/research/whatweb
