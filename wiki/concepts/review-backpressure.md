---
type: concept
tags: [ai-agents, code-review, automation, flow-control]
updated: 2026-10-27
---

# Review Backpressure

Review backpressure is a limit on automated change production when human review has not caught up. In [[loop-engineering-from-first-principles]], each coding loop labels its PRs and checks for an earlier open PR with that label before doing more work. If one is open, the scheduled run exits without creating another proposal.

This gate keeps the loop's output within its reviewers' capacity. It also reduces duplicate migrations and merge conflicts caused by stacked PRs. The source presents one open PR per loop as a conservative policy; a team can adjust concurrency only when review ownership and change size support it.

## Related Pages

- [[loop-engineering]]
- [[agent-loop-guardrails]]
- [[verifier-bottleneck]]
- [[software-factories]]
