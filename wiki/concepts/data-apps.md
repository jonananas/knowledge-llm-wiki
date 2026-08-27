---
type: concept
tags: [data-visualization, dashboards, product-analytics, developer-tools]
updated: 2026-08-27
---

# Data Apps

Data apps are durable interactive applications whose primary purpose is to present, explore, or communicate data. They can include dashboards, reports, coordinated visualizations, monitoring views, analytical tools, and quantitative narratives.

The [[observable-2-0]] source contrasts data apps with notebooks. Notebooks are optimized for ad hoc exploration, learning, and fast local thought. Data apps are more often team-facing artifacts that people revisit, so they need stronger presentation, performance, maintainability, and deployment practices.

## Characteristics

- Higher visual information density than a notebook.
- Less editor chrome and more polished presentation.
- Interactive charts, controls, and coordinated views.
- Repeatable publication and deployment.
- Reviewable source files, tests, and CI/CD where the app influences team decisions.
- Clearer separation between data preparation and presentation.

## Design Tension

Data apps sit between analysis and software. If they stay too close to notebooks, they may be hard to maintain, too slow, or awkward for non-author users. If they become full custom applications too early, teams may overinvest before proving the analysis is valuable.

[[observable-framework]] argues for a middle path: code-first local files and static-site deployment, with [[build-time-data-loaders]] handling data preparation before the user loads the app.

## Related Pages

- [[observable]]
- [[observable-framework]]
- [[observable-2-0]]
- [[build-time-data-loaders]]
