---
type: entity
tags: [data-visualization, dashboards, static-site-generators, javascript]
updated: 2026-08-27
---

# Observable Framework

Observable Framework is an open-source static site generator for [[data-apps]], dashboards, and reports. It combines JavaScript in the browser for interactive graphics with [[build-time-data-loaders]] that can prepare data in SQL, Python, R, Rust, Go, or other languages. [[observable-2-0]]

## Role

Observable Framework is best understood as a code-first alternative to stretching computational notebooks into polished dashboard and reporting use cases. It gives data teams local files, git, review, tests, CI/CD, offline work, self-hosting, and deployment automation while still keeping the frontend optimized for interactive data visualization.

## Architecture

- Pages are written as Markdown with interactive JavaScript.
- Frontend code can use charts, inputs, responsive grids, themes, dark mode, and other dashboard-oriented UI features.
- Data loaders run at build time and emit static files consumed by the browser.
- Loaders can use different languages and data sources, so teams can keep existing analysis tools while producing web-friendly artifacts.
- Static snapshots reduce load-time query work and can limit what client-side users receive.

## Relationship To Notebooks

The [[observable-2-0]] source treats notebooks and Framework as complementary rather than interchangeable. Notebooks are strongest for exploration, learning, and quick iteration where code and output should stay adjacent. Framework targets durable team-facing applications where presentation, performance, maintainability, and deployment practices matter more.

## Follow-ups

- [ ] [Getting started](https://observablehq.com/framework/getting-started) - capture setup flow, required Node version, and generated project structure.
- [ ] [Deploying](https://observablehq.com/framework/deploying) - capture hosting model and CI/CD guidance.

## Related Pages

- [[observable]]
- [[observable-2-0]]
- [[data-apps]]
- [[build-time-data-loaders]]
