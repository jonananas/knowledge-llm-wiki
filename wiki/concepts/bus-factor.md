---
type: concept
tags: [software-engineering, teams, maintenance, risk]
updated: 2026-08-27
---

# Bus Factor

Bus factor is the risk created when critical knowledge is concentrated in too few people. A low bus factor means the project may struggle if one key contributor leaves, becomes unavailable, or stops maintaining a major subsystem.

The [[git-commands-before-reading-code]] source uses `git shortlog -sn --no-merges` as a crude bus-factor screen. If one person accounts for most commits, or if the top historical contributor is absent from recent history, the project may have lost important context.

## Caveats

Commit counts are an imperfect proxy for ownership. Squash merges, pair programming, generated commits, and merge policies can distort authorship. Bus factor should be checked with team context, code ownership, documentation, review patterns, and recent activity.

## Related Pages

- [[git-commands-before-reading-code]]
- [[git-history-analysis]]
- [[codebase-audits]]
- [[code-churn-hotspots]]
