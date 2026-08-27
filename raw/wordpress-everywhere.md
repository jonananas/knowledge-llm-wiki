# WordPress Everywhere

Source URL: https://ma.tt/2026/03/wordpress-everywhere/
Fetch date: 2026-08-27

Author: Matt Mullenweg
Published: 2026-03-11

Related links:
- my.WordPress.net announcement: https://wordpress.org/news/2026/03/announcing-my-wordpress/
- my.WordPress.net: https://my.wordpress.net/
- WordPress Playground: https://wordpress.org/playground/
- WordPress Playground docs: https://developer.wordpress.org/playground/

## Summary

Matt Mullenweg's "WordPress Everywhere" argues that my.WordPress.net and WordPress Playground should change how people think about WordPress. Instead of only treating WordPress as hosted software from WordPress.com, Bluehost, Hostinger, Pressable, or another web host, he frames it as a self-contained open-source software unit that can run in the browser, on devices, in development environments, and eventually sync or publish to the cloud.

The concrete technical shift is WebAssembly-based WordPress Playground. Mullenweg says it can spin up a web server, a database such as SQLite or MariaDB, and a full WordPress installation inside the browser in about 30 seconds. He presents Playground containers as composable and atomic, with changes that can be tracked and rolled back.

The philosophical claim is that WordPress should be understood as infrastructure for digital sovereignty: a piece of the internet people own and control, backed by open source, backwards compatibility, exportability, and long-term institutional commitment.

## Main points

- my.WordPress.net had soft-launched at the time of the post.
- Mullenweg argues that WordPress should no longer be seen only as hosted web software.
- WordPress Playground uses WebAssembly to run WordPress without a traditional server.
- The browser environment can include a web server, database, and full WordPress installation.
- Playground makes WordPress local, fast, and easy to spin up for multiple instances.
- Mullenweg frames this as a strong fit for AI-assisted experimentation because agents can test code changes inside local, disposable WordPress instances.
- Planned next steps named in the post include peer-to-peer sync, version-control integration, and cloud publishing.
- Mullenweg predicts this could move WordPress from millions of instances to billions.
- He argues cloud hosting will not disappear; instead, demand for cloud sync and publishing may increase.
- The post contrasts open source and long-term stewardship with AI-era software that is easy to generate but may not endure.
- WordPress's backwards compatibility, exportability, permalink maintenance, and WordPress.com 100-year plans are used as evidence for long-term durability.
- The post argues that, in the future, everyone should have a domain and a WordPress as part of their personal internet ownership.

## Official my.WordPress.net details

The WordPress.org announcement describes my.WordPress.net as persistent WordPress in the browser with no sign-up, hosting plan, or domain decision required up front. It is private by default and not reachable from the public internet. It is positioned as a personal workspace for thinking, drafting, organizing, experimentation, learning, and small tools.

The announcement lists app-like starting points such as a personal CRM, personal RSS reader, and AI workspace/knowledge base. It also notes operational constraints:

- Storage starts at roughly 100 MB.
- First launch is slower while WordPress downloads and initializes.
- Data stays in the browser and is not uploaded.
- Each device has a separate installation.
- Users should download backups regularly.

## Interpretation

The source is part product announcement and part open-web thesis. Its most reusable technical idea is browser-local software: a full open-source application runtime can live locally in the browser, with later sync or publish steps layered on top. That creates a different adoption path from traditional hosting, because users can begin privately and locally before deciding whether to publish.

The AI angle is practical rather than only rhetorical. If WordPress instances are fast, local, rollbackable, and easy to duplicate, they become safer targets for AI-assisted plugin edits, theme experiments, demos, and migration tests.

## Links

- Matt Mullenweg post: https://ma.tt/2026/03/wordpress-everywhere/
- WordPress.org announcement: https://wordpress.org/news/2026/03/announcing-my-wordpress/
- my.WordPress.net: https://my.wordpress.net/
- WordPress Playground: https://wordpress.org/playground/
- Playground docs: https://developer.wordpress.org/playground/
