---
type: concept
tags: [documentation, developer-tools]
updated: 2026-08-26
---

# Documentation Frameworks

Documentation frameworks provide reusable structure, routing, navigation, search, theming, content loading, and authoring features for product or developer documentation sites.

The [[fumadocs-homepage]] source positions [[fumadocs]] as a documentation framework for React projects, with both ready-made UI and headless pieces that developers can compose into custom docs experiences.

## Common Capabilities

- Markdown or MDX authoring.
- Navigation and sidebar generation.
- Syntax highlighting for code examples.
- Search integration.
- Theming and layout primitives.
- API reference or OpenAPI rendering.
- Content loading from files, CMSs, or custom sources.
- Extension through plugins or content-processing pipelines.

## Design Tension

Documentation frameworks sit between two needs: teams want strong defaults so docs can ship quickly, but they also want control because documentation is part of a product's interface and brand. Fumadocs explicitly leans into this tension by offering designed themes alongside headless and composable packages. [[fumadocs-homepage]]

## Related Pages

- [[fumadocs]]
- [[mdx-documentation]]
