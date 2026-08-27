---
type: source
tags: [git, code-review, codebase-audits, technical-debt]
updated: 2026-08-27
source_url: https://piechowski.io/post/git-commands-before-reading-code/
---

# The Git Commands I Run Before Reading Any Code

Source: [Ally Piechowski](https://piechowski.io/post/git-commands-before-reading-code/). Raw capture: [raw/git-commands-before-reading-code.md](../../raw/git-commands-before-reading-code.md).

[[ally-piechowski]] argues that Git history should be read before source code during [[codebase-audits]]. The post, published on 2026-04-08 and updated on 2026-07-08, gives five lightweight commands for [[git-history-analysis]]: code churn, contributor concentration, bug-fix clusters, monthly activity, and firefighting patterns.

The strongest practical idea is that Git metadata can tell an auditor where to look first. It does not diagnose architecture by itself, but it reveals hotspots, ownership gaps, and process instability that should guide later code reading.

## Commands

```sh
git log --format=format: --name-only --since="1 year ago" | sort | uniq -c | sort -nr | head -20
git shortlog -sn --no-merges
git log -i -E --grep="fix|bug|broken" --name-only --format='' | sort | uniq -c | sort -nr | head -20
git log --format='%ad' --date=format:'%Y-%m' | sort | uniq -c
git log --oneline --since="1 year ago" | grep -iE 'revert|hotfix|emergency|rollback'
```

## Key Points

- High file churn is a starting signal, not proof of bad code.
- [[code-churn-hotspots]] become more meaningful when cross-checked against bug-fix clusters.
- Contributor concentration can expose [[bus-factor]] risk, especially when the dominant historical contributor is no longer active.
- Commit velocity over time can reveal project momentum, team departures, or release batching.
- Reverts, hotfixes, emergency commits, and rollbacks can indicate testing, staging, or deployment weakness.
- Squash merges, generated files, lockfiles, changelogs, repository layout, and weak commit messages can distort the results.

## Interpretation

This source is useful because it treats Git as a diagnostic data source rather than only a version-control tool. The commands are deliberately crude, but the workflow is disciplined: gather cheap signals, compare them, then decide what code deserves attention first.

The source also reinforces a broader audit principle: organizational risk and technical risk are often coupled. A fragile file, a departed owner, and repeated hotfixes around the same area tell a stronger story together than any one metric does alone.

## Follow-ups

- [ ] [Your Code as a Crime Scene](https://pragprog.com/titles/atcrime/your-code-as-a-crime-scene/) - capture Adam Tornhill's fuller churn-and-complexity methodology.
- [ ] [Use of Relative Code Churn Measures to Predict System Defect Density](https://www.microsoft.com/en-us/research/publication/use-of-relative-code-churn-measures-to-predict-system-defect-density/) - capture the 2005 Microsoft Research study cited by the post.
- [ ] [How I Audit a Legacy Rails Codebase in the First Week](https://piechowski.io/post/how-i-audit-a-legacy-rails-codebase/) - capture the broader codebase-audit workflow.

## Related Pages

- [[ally-piechowski]]
- [[codebase-audits]]
- [[git-history-analysis]]
- [[code-churn-hotspots]]
- [[bus-factor]]
