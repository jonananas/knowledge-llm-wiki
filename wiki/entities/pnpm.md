---
type: entity
tags: [javascript, nodejs, package-management, monorepos]
updated: 2026-08-26
---

# pnpm

pnpm is a JavaScript package manager built around a global content-addressable package store and hard-linked project installs. In [[pnpm-vs-npm-vs-yarn-vs-bun-2026]], it is framed as the "safe modern choice": faster and more disk-efficient than npm while preserving a mostly traditional `node_modules` workflow.

## Strengths

- Strong disk efficiency across many projects with overlapping dependencies.
- Good compatibility because projects still see a `node_modules` structure.
- Strong workspace and monorepo support, including filtering and strict dependency isolation.
- Native audit and SBOM paths according to the source article.

## Tradeoffs

The article notes that pnpm's stricter `node_modules` structure can expose packages that rely on undeclared or incorrectly hoisted dependencies. The workaround mentioned is `shamefully-hoist=true`, but that weakens the strictness that makes pnpm useful.

## Related Pages

- [[javascript-package-management]]
- [[javascript-monorepo-package-management]]
- [[javascript-package-manager-selection]]
