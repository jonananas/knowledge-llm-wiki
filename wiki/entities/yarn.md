---
type: entity
tags: [javascript, nodejs, package-management, monorepos]
updated: 2026-08-26
---

# Yarn

Yarn is a JavaScript package manager. The article [[pnpm-vs-npm-vs-yarn-vs-bun-2026]] focuses on Yarn 4 / Berry, positioning it as an innovation-heavy choice around Plug'n'Play, zero-installs, plugin architecture, offline-first workflows, and strong workspace features.

## Tradeoffs

Yarn's Plug'n'Play model can eliminate `node_modules`, but the article treats that as both powerful and divisive because some packages and tools still expect traditional filesystem layout. Teams can use `nodeLinker: node-modules` for compatibility when needed.

## Related Pages

- [[javascript-package-management]]
- [[javascript-monorepo-package-management]]
- [[javascript-package-manager-selection]]
