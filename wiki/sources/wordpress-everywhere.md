---
type: source
tags: [wordpress, open-source, webassembly, browser-local, ai]
updated: 2026-08-27
source_url: https://ma.tt/2026/03/wordpress-everywhere/
---

# WordPress Everywhere

Source: [Matt Mullenweg](https://ma.tt/2026/03/wordpress-everywhere/). Raw capture: [raw/wordpress-everywhere.md](../../raw/wordpress-everywhere.md).

Matt Mullenweg's March 2026 essay argues that [[my-wordpress-net]] and [[wordpress-playground]] should change how people think about [[wordpress]]. Instead of treating WordPress primarily as hosted CMS software, he frames it as a portable, browser-runnable, open-source unit of software that can support [[browser-local-software]], AI-assisted experimentation, cloud publishing, and [[digital-sovereignty]].

The concrete product event is the soft launch of [[my-wordpress-net]]. The broader thesis is that WebAssembly makes it possible to run a full WordPress environment locally in the browser, then later add peer-to-peer sync, version-control integration, and cloud publishing.

## Key Points

- [[wordpress-playground]] can run a web server, database, and WordPress in the browser using WebAssembly.
- Mullenweg says a full browser WordPress can start in about 30 seconds.
- Playground containers are presented as composable and atomic, with changes that can be tracked and rolled back.
- This changes WordPress from something users must first obtain through hosting into a local, private, recoverable software environment.
- Mullenweg explicitly connects this to AI: local, fast, disposable WordPress instances make it easier for AI systems to test code changes and save results.
- Planned next steps include peer-to-peer sync, version-control integration, and cloud publishing.
- The essay argues that hosting demand may increase rather than disappear, because browser-local WordPress will create more demand for sync and publishing.
- The long-term trust argument rests on open source, backwards compatibility, exportability, permalink stewardship, and WordPress.com's 100-year plans.
- The official WordPress.org announcement adds product constraints: my.WordPress.net is private by default, stores data in the browser, starts with roughly 100 MB of storage, uses separate installations per device, and requires regular backup downloads.

## Interpretation

The reusable technical pattern is [[browser-local-software]]: start with a full local runtime in the browser, then layer sync, version control, publishing, and collaboration on top. This reverses the normal CMS adoption path where users must choose hosting, public identity, and infrastructure before they can safely experiment.

The source also sharpens [[digital-sovereignty]] as a product strategy. Mullenweg is not only arguing for open-source licensing; he is arguing for durable user control over code, data, domain identity, backups, exports, and long-term availability.

## Follow-ups

- [ ] [WordPress Playground docs](https://developer.wordpress.org/playground/) - capture architecture, Blueprints, browser storage, Node.js use, and AI-assistant integration details.
- [ ] [WordPress Playground repository](https://github.com/WordPress/wordpress-playground) - inspect implementation, licensing, and WebAssembly runtime structure.
- [ ] [my.WordPress.net announcement](https://wordpress.org/news/2026/03/announcing-my-wordpress/) - ingest as a product-specific source if my.WordPress.net becomes central.
- [ ] [Blocknotes](https://blocknotes.org/) - inspect the cross-publishing example mentioned in the essay.

## Related Pages

- [[wordpress]]
- [[matt-mullenweg]]
- [[automattic]]
- [[wordpress-playground]]
- [[my-wordpress-net]]
- [[browser-local-software]]
- [[digital-sovereignty]]
- [[sandboxed-code-execution]]
