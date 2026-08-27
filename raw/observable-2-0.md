# Observable 2.0

Source URL: https://observablehq.com/blog/observable-2-0
Fetch date: 2026-08-27

Author: Mike Bostock
Published: 2024-02-15

Related links:
- Observable Framework: https://observablehq.com/framework/
- Framework docs: https://observablehq.com/framework/what-is-framework
- Data loaders: https://observablehq.com/framework/data-loaders
- Framework repository: https://github.com/observablehq/framework

## Summary

Observable announced Observable 2.0 around Observable Framework: an open-source static site generator for data apps, dashboards, and reports. The post frames the launch as a shift beyond Observable notebooks. Notebooks remain useful for ad hoc exploration, tinkering, and learning, but they are not ideal for polished, maintained dashboards or team-facing data applications.

Observable Framework combines JavaScript in the browser for interactive graphics with data preparation in any backend language. Projects are ordinary local files, so teams can use normal development workflows: editors, git, code review, tests, CI/CD, offline work, self-hosting, or hosted deployment on Observable.

## Main points

- Observable 2.0 introduces Observable Framework as a code-first way to build data apps.
- The post distinguishes notebooks from data apps: notebooks are good for exploration, while data apps need higher information density, polished presentation, maintainability, performance, and team use.
- Observable's stated goals are a better developer workflow, a better user experience, and a better data architecture.
- Framework uses local files and vanilla JavaScript syntax, moving closer to conventional web development workflows.
- It supports Markdown pages with interactive charts, inputs, responsive grids, themes, dark mode, and keyboard-friendly navigation.
- It can combine JavaScript on the frontend with SQL, Python, R, Rust, Go, or other languages for data preparation.
- Data loaders solve the "last mile" problem by generating static data snapshots at build time.
- Build-time snapshots make dashboards faster because users are not waiting for live database queries on page load.
- Build-time data can be optimized, aggregated, or anonymized before being sent to the browser.
- Because data loaders run on the developer's or team's infrastructure, viewers do not need direct access to underlying databases or data warehouses.
- Framework projects can be hosted anywhere or deployed to Observable for secure sharing with a team.

## Interpretation

The post's strongest architectural claim is that dashboard performance and data access should move from request time to build time when possible. Data loaders become a middle layer between data engineering and frontend visualization: they can use whatever language and source system the team needs, but produce static files for fast, robust client-side presentation.

This also reframes the role of notebooks. Rather than making notebooks stretch into every presentation use case, Observable 2.0 treats notebooks as exploratory tools and data apps as durable software artifacts that benefit from files, source control, tests, review, and deployment automation.

## Links

- Blog post: https://observablehq.com/blog/observable-2-0
- Observable Framework: https://observablehq.com/framework/
- What is Framework: https://observablehq.com/framework/what-is-framework
- Data loaders: https://observablehq.com/framework/data-loaders
- GitHub repository: https://github.com/observablehq/framework
