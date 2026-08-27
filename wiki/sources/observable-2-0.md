---
type: source
tags: [data-visualization, dashboards, static-site-generators, developer-tools]
updated: 2026-08-27
source_url: https://observablehq.com/blog/observable-2-0
---

# Observable 2.0

Source: [Observable blog](https://observablehq.com/blog/observable-2-0). Raw capture: [raw/observable-2-0.md](../../raw/observable-2-0.md).

Mike Bostock's Observable 2.0 announcement introduces [[observable-framework]] as the centerpiece of Observable's shift beyond notebooks: an open-source static site generator for [[data-apps]], dashboards, and reports.

The post argues that Observable notebooks are useful for ephemeral and ad hoc data exploration, but polished dashboards and team-facing data applications need a different workflow: higher information density, less editor chrome, better user experience, performance, maintainability, tests, code review, and deployment automation.

## Key Points

- [[observable]] frames Observable 2.0 around a new product direction: code-first data apps rather than notebooks as the single interface for all data work.
- [[observable-framework]] combines browser-side JavaScript for interactive graphics with data preparation in SQL, Python, R, Rust, Go, or other backend languages.
- Framework projects are ordinary local files, so developers can use editors, git, code review, tests, CI/CD, offline work, self-hosting, and programmatic editing.
- The post treats vanilla JavaScript and ES imports as part of making Observable easier to learn and easier to integrate with other applications.
- Framework's biggest architectural claim is [[build-time-data-loaders]]: data loaders run during build to generate static snapshots used by the client.
- Build-time snapshots are framed as faster, more secure, and more robust than dashboards that run database queries when each viewer loads a page.
- The post treats data preparation as the bulk of visualization work and argues for letting teams use any language, library, or data source for that preparation.

## Interpretation

The practical lesson is that durable analytical interfaces should often be treated as software, not notebook byproducts. A notebook is optimized for fast local thought. A data app is optimized for repeated use by a team, so it benefits from conventional software workflows and from an architecture that precomputes data where possible.

Observable Framework's data-loader model is also a useful general pattern: keep the browser interactive, but move slow or privileged data work into reproducible build steps that emit minimized static artifacts. That can improve page speed, reduce database exposure, and let teams validate an analytical idea before pushing more work into the data warehouse.

## Follow-ups

- [ ] [Observable Framework docs](https://observablehq.com/framework/) - capture current project structure, Markdown, JavaScript, themes, and deployment model.
- [ ] [Observable Framework data loaders](https://observablehq.com/framework/data-loaders) - capture details of routing, execution, caching, and CI behavior.
- [ ] [Observable Framework repository](https://github.com/observablehq/framework) - track implementation, license, release cadence, and examples.
- [ ] [Observable Plot](https://observablehq.com/plot/) - capture the visualization library commonly paired with Framework.

## Related Pages

- [[observable]]
- [[observable-framework]]
- [[data-apps]]
- [[build-time-data-loaders]]
