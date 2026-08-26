---
type: source
tags: [developer-tools, documentation, react, mdx]
updated: 2026-08-26
source_url: https://www.fumadocs.dev/
---

# Fumadocs Homepage

Source: [Fumadocs](https://www.fumadocs.dev/). Raw capture: [raw/fumadocs-homepage.md](../../raw/fumadocs-homepage.md).

## Summary

The Fumadocs homepage presents [[fumadocs]] as a React documentation framework with polished default themes, headless customization, Markdown and MDX authoring, and portability across React frameworks such as Next.js, Waku, TanStack Start, and React Router.

The most important architectural claim is composability. The homepage describes Fumadocs as separated into Content, Core, and UI layers, with packages for MDX, core docs handling, UI, OpenAPI docs, and Obsidian-style Markdown.

## Key Takeaways

- Fumadocs is aimed at teams that want to avoid rebuilding a full docs site for each project.
- It combines designed themes with a headless mode for teams that want their own UI.
- It supports conventional Markdown features and extended docs features such as Shiki syntax highlighting, callouts, cards, codeblock groups, custom anchors, and automatic tables of contents.
- It supports [[mdx-documentation]] workflows with custom components, includes, TypeScript Twoslash, Storybook integration, and remark/rehype plugins.
- React Server Components are framed as a way to keep docs connected to server-side data, databases, CMSs, type metadata, or OpenAPI playgrounds.
- The project is positioned as framework-agnostic within the React ecosystem.
- Search integrations include Orama Search and Algolia Search.
- The homepage presents Fumapress as a simpler plugin-based layer for people who want Fumadocs without as much configuration.

## Connections

- [[fumadocs]] - central tool.
- [[documentation-frameworks]] - category Fumadocs belongs to.
- [[mdx-documentation]] - content-authoring workflow Fumadocs emphasizes.

## Follow-ups

- [ ] [Fumadocs documentation](https://www.fumadocs.dev/docs) - capture installation, routing, content loading, search, and deployment details.
- [ ] [Fumadocs GitHub repository](https://github.com/fuma-nama/fumadocs) - capture package structure, license, release cadence, and ecosystem maturity.
- [ ] [Fumapress](https://press.fumadocs.dev/) - capture the simplified plugin-based framework built around Fumadocs.
