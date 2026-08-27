---
type: concept
tags: [data-visualization, dashboards, static-site-generators, data-engineering]
updated: 2026-08-27
---

# Build-Time Data Loaders

Build-time data loaders are scripts or programs that prepare data during a site or app build and emit static artifacts for the frontend to load. In [[observable-framework]], loaders can be written in languages such as SQL, Python, R, Rust, Go, or JavaScript, then produce static snapshots for dashboards and reports. [[observable-2-0]]

## Why They Matter

Dashboards are often slow when each viewer triggers live queries at page load. Build-time loaders shift that work earlier:

- Expensive data preparation happens once during build instead of once per viewer.
- The browser receives precomputed, smaller, and more targeted data files.
- Sensitive source systems can stay behind the build process.
- Data can be aggregated or anonymized before publication.
- Teams can host the resulting app as static files when live querying is unnecessary.

## Tradeoffs

Build-time loading is strongest when data can be refreshed on a schedule, on commit, or through deployment automation. It is weaker when the app requires truly live state, per-user authorization at query time, or low-latency writes back to source systems.

The key design question is freshness versus performance and exposure. If a dashboard can tolerate periodic rebuilds, build-time snapshots can simplify runtime architecture and improve user experience. If it cannot, runtime fetching or a backend service may still be needed.

## Related Pages

- [[observable-framework]]
- [[observable-2-0]]
- [[data-apps]]
