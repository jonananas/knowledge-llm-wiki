---
type: entity
tags: [developer-tools, documentation, react, mdx]
updated: 2026-08-26
---

# Fumadocs

Fumadocs is an open-source React documentation framework for building customizable docs sites. Its homepage emphasizes strong default themes, headless customization, Markdown and MDX authoring, content-source flexibility, and portability across React frameworks. [[fumadocs-homepage]]

## Positioning

Fumadocs is aimed at developers who would otherwise rebuild the same docs-site structure for every project. It offers reusable documentation building blocks rather than only a fixed template, and it can be used as a full framework or as lower-level libraries.

## Architecture

The homepage describes Fumadocs as separated into three layers:

- Content: loading and adapting documentation content.
- Core: headless docs logic and content handling.
- UI: components and themes for the visible documentation experience.

Named packages include `fumadocs-mdx`, `fumadocs-core`, `fumadocs-ui`, `fumadocs-openapi`, and `fumadocs-obsidian`.

## Capabilities Highlighted

- CLI project creation through `pnpm create fumadocs-app`.
- Support for Next.js, Waku, TanStack Start, and React Router.
- Markdown and MDX content.
- Shiki syntax highlighting and Shiki notations.
- Codeblock groups, callouts, cards, heading anchors, and automatic tables of contents.
- TypeScript Twoslash for richer code examples.
- Storybook and OpenAPI documentation integration.
- Search integration with Orama Search and Algolia Search.
- Support for MDX, Content Collections, custom CMSs, BaseHub, Sanity, and Payload.

## Related Pages

- [[documentation-frameworks]]
- [[mdx-documentation]]

## Follow-ups

- [ ] [Fumadocs docs](https://www.fumadocs.dev/docs) - document actual setup and content-source patterns.
- [ ] [Fumadocs GitHub](https://github.com/fuma-nama/fumadocs) - capture package structure and project health.
- [ ] [Fumadocs Showcase](https://www.fumadocs.dev/showcase) - collect examples of real-world docs sites using it.
