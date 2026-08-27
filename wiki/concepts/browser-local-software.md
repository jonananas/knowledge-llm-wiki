---
type: concept
tags: [webassembly, browser-local, developer-tools, personal-software]
updated: 2026-08-27
---

# Browser-Local Software

Browser-local software is software that runs a substantial application runtime inside the user's browser rather than requiring a traditional hosted server before use. It can use technologies such as WebAssembly, browser storage, local-first data models, and later sync or publishing layers.

The [[wordpress-everywhere]] source makes this concrete through [[wordpress-playground]] and [[my-wordpress-net]]: a web server, database, and full [[wordpress]] installation can run in the browser, giving users a private local environment before they decide whether to publish or sync.

## Why It Matters

- Removes early hosting, account, and domain decisions from experimentation.
- Lets users start privately and publish later.
- Creates fast, disposable environments for learning, testing, and demos.
- Gives AI assistants safer targets for code changes and plugin experiments.
- Can preserve user control when paired with export, backups, and open formats.

## Tradeoffs

Browser-local software still has operational constraints: storage limits, browser compatibility, per-device state, backup responsibility, and sync complexity. It can reduce server dependence for initial use, but does not eliminate the need for hosting when users want collaboration, public access, or reliable multi-device availability.

## Related Pages

- [[wordpress-everywhere]]
- [[wordpress-playground]]
- [[my-wordpress-net]]
- [[sandboxed-code-execution]]
- [[digital-sovereignty]]
