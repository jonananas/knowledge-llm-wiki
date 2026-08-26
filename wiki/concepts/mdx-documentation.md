---
type: concept
tags: [documentation, mdx, react, content]
updated: 2026-08-26
---

# MDX Documentation

MDX documentation uses Markdown for prose while allowing JSX components and JavaScript expressions inside documentation pages. This lets docs combine normal writing with interactive examples, custom UI, generated reference tables, and live data.

The [[fumadocs-homepage]] source highlights MDX as a core Fumadocs workflow. It mentions custom components, include/embed content, TypeScript Twoslash, Storybook integration, Shiki notations, and remark/rehype extension points.

## Strengths

- Writers can keep most content in familiar Markdown.
- Developers can embed React components where documentation needs richer behavior.
- Code examples can be enhanced with syntax highlighting, annotations, and type information.
- Docs can pull from live or generated sources, including databases, CMSs, TypeScript metadata, or OpenAPI definitions.

## Risks

MDX can blur the boundary between content and application code. It is powerful for engineering-heavy docs, but teams need conventions around component APIs, content review, build behavior, and what belongs in prose versus executable UI.

## Related Pages

- [[fumadocs]]
- [[documentation-frameworks]]
