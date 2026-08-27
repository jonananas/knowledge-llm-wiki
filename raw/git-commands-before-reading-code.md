# The Git Commands I Run Before Reading Any Code

Source URL: https://piechowski.io/post/git-commands-before-reading-code/
Fetch date: 2026-08-27

Author: Ally Piechowski
Published: 2026-04-08
Updated: 2026-07-08

Related links:
- Microsoft Research churn study linked by the post: https://www.microsoft.com/en-us/research/publication/use-of-relative-code-churn-measures-to-predict-system-defect-density/
- Your Code as a Crime Scene: https://pragprog.com/titles/atcrime/your-code-as-a-crime-scene/
- Related post, legacy Rails audit: https://piechowski.io/post/how-i-audit-a-legacy-rails-codebase/

## Summary

Ally Piechowski argues that the first step in understanding a new codebase is not opening files but reading Git history. Five short Git commands can reveal where the code changes most, who built it, where bug fixes cluster, whether the project is active or fading, and how often the team is firefighting.

The post frames Git history as a cheap diagnostic map. It does not replace reading code, but it tells the reviewer what code to read first and what organizational risks to watch for.

## Commands

Most-changed files in the last year:

```sh
git log --format=format: --name-only --since="1 year ago" | sort | uniq -c | sort -nr | head -20
```

Contributor count:

```sh
git shortlog -sn --no-merges
```

Bug-fix file clusters:

```sh
git log -i -E --grep="fix|bug|broken" --name-only --format='' | sort | uniq -c | sort -nr | head -20
```

Commits by month:

```sh
git log --format='%ad' --date=format:'%Y-%m' | sort | uniq -c
```

Reverts, hotfixes, emergency changes, and rollbacks:

```sh
git log --oneline --since="1 year ago" | grep -iE 'revert|hotfix|emergency|rollback'
```

## Main points

- Run churn analysis from `app/` or `src/`, not the repo root, so generated files, lockfiles, and changelogs do not dominate.
- High churn alone does not prove bad design; it may reflect active feature work.
- High churn plus high bug-fix frequency is a stronger signal of risky code.
- `git shortlog` shows ownership concentration and possible bus factor risk.
- If the top historical contributor is absent from the recent six-month window, the project may have lost key context.
- Squash-merge workflows can distort contributor counts because they may show who merged rather than who authored.
- Bug-cluster detection depends on commit-message discipline.
- Monthly commit counts can reveal team changes, project decline, release batching, or shipping rhythm.
- Revert and hotfix frequency can reveal unstable tests, staging, or deployment processes.
- Zero crisis-keyword results can mean stability, but can also mean poor commit messages.

## Interpretation

The post's useful pattern is "history before source." Git metadata provides a first-pass map of code and team risk before detailed code reading begins. The strongest signals come from cross-checking metrics rather than treating any single command as proof: high churn plus bug-cluster overlap, ownership concentration plus recent absence, or revert frequency plus deployment context.

The caveats are important. Git history is shaped by merge strategy, generated files, commit hygiene, release style, and repository layout. The commands are screening tools, not final diagnoses.

## Links

- Blog post: https://piechowski.io/post/git-commands-before-reading-code/
- Author site: https://piechowski.io/
