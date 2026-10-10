---
name: git-rp-workflow
description: Do git work safely and professionally across three areas - pull requests (commit messages, branch names, PR descriptions, code review, merge conflicts), roleplay (RP) projects kept in a repo (character sheets, scenes, session logs, canon tracking, alternate timelines), and release management (semantic versioning, tags, changelogs, branching strategy), plus recovery from git mistakes. Use this skill whenever the user mentions git, commits, branches, PRs or pull requests, merge conflicts, rebase, tags, releases, changelogs, or wants to organize a roleplay, story or worldbuilding project in a repository, even if they only say "RP git" or "help me with my repo".
---

# Git & RP Workflow

One consistent, safe process for three kinds of repository work. Detailed templates live in `references/` and are loaded only for the track you need.

| Track | Use for | Read |
|---|---|---|
| **A. Pull requests** | commits, branch names, PR descriptions, reviews, merge conflicts | `references/pull-requests.md` |
| **B. Roleplay repos** | characters, world, scenes, session logs, canon, alternate timelines | `references/roleplay-repos.md` |
| **C. Releases** | versioning, tags, changelog, branching strategy, repo housekeeping | `references/releases.md` |
| **Recovery** | wrong branch, bad reset, leaked secret, messy merge | `references/recovery.md` |

If a request spans tracks, handle them in the order the user listed them.

## Step 0: Orient before acting

Most git mistakes come from acting on a wrong picture of the current state, so look first.

1. Run `git status`, `git branch --show-current` and `git log --oneline -10`.
2. Look for the repo's own conventions: `CONTRIBUTING.md`, `.github/pull_request_template.md`, existing commit style, `CHANGELOG.md`. A repo's established habits beat the defaults in this skill.
3. Identify the track and read its reference file.
4. If the request is ambiguous on something that changes the outcome (which branch, which remote, which version number), ask one short question rather than guess.

## Safety rules

These protect work that other people, or the user's future self, depend on. Explain the reason when you ask for confirmation.

- **Shared history is shared.** Force-pushing to `main`, `master`, `develop` or a release branch can erase teammates' commits, so do not do it. On the user's own feature branch, `--force-with-lease` is acceptable after they confirm.
- **Published history stays put.** Rebase, amend and filter-branch rewrite commits others may have pulled, so get explicit approval first.
- **Destructive commands need a preview.** Before `reset --hard`, `clean -fd`, `branch -D` or `checkout -- .`, show what will be lost and offer `git stash` or a `backup/<name>` branch as the safer route.
- **Secrets are burned once committed.** If a token or `.env` was committed, tell the user to rotate it, because deleting it from history does not undo exposure.
- **Keep the repo lean.** Avoid committing large binaries or generated files unless the repo already does; suggest Git LFS or `.gitignore`.
- **Small reversible steps.** Before a multi-step operation, create `git branch backup/<name>`.
- **Publishing is the user's call.** Push, open a PR, or tag only when asked.

## Communication

Before a command that changes state, show the exact command with a one-line reason. After finishing, report what changed, the current branch and state, and the next step (for example "committed locally, not pushed").

**Example**
Input: "commit my changes"
Output:
```
Staged: src/auth.py, tests/test_auth.py
Commit: fix(auth): reject expired tokens before refresh
Not pushed. Want me to push or open a PR?
```

## Final self-check
- Did I inspect the repo state before acting?
- Did any action risk lost work, and did I get confirmation first?
- Did I avoid pushing, tagging or opening a PR unasked?
- Does the output follow this repo's own conventions?
- For RP work: is new material consistent with canon and each character's voice?
