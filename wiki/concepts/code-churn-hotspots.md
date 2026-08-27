---
type: concept
tags: [software-engineering, technical-debt, code-review, maintenance]
updated: 2026-08-27
---

# Code Churn Hotspots

Code churn hotspots are files or modules that change unusually often over a period of time. In [[git-commands-before-reading-code]], [[ally-piechowski]] uses churn as a first-pass signal for where an auditor should look before reading a new codebase.

## Interpretation

High churn does not automatically mean bad code. It can mean active development. The signal becomes stronger when churn overlaps with other evidence:

- The same files appear in bug-fix commit clusters.
- Nobody wants to own the files.
- Estimates grow because changes have unpredictable blast radius.
- The original author or dominant maintainer is no longer active.

## Use In Audits

During [[codebase-audits]], churn hotspots help prioritize reading order. A high-churn, high-bug file is often a better first target than a large but stable file.

## Related Pages

- [[git-commands-before-reading-code]]
- [[git-history-analysis]]
- [[codebase-audits]]
- [[bus-factor]]
