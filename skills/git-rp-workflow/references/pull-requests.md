# Track A: Pull Requests

## Contents
- Commits
- Branch names
- PR description
- Reviewing a PR
- Resolving conflicts

## Commits
Use Conventional Commits unless the repo uses another style:

```
<type>(<scope>): <imperative summary, up to ~72 chars>

<body: what changed and why, wrapped at ~72 columns>

<footer: issue refs, BREAKING CHANGE>
```

Types: `feat`, `fix`, `docs`, `refactor`, `test`, `chore`, `perf`, `ci`, `build`.

- One logical change per commit, so each can be reviewed and reverted alone.
- Imperative mood ("add", not "added"), matching git's own messages.
- Explain *why* in the body; the diff already shows *what*.
- Mark breaking changes with `!` or a `BREAKING CHANGE:` footer so tooling and readers catch them.

**Example 1**
Input: Added user authentication with JWT tokens
Output: `feat(auth): implement JWT-based authentication`

**Example 2**
Input: fixed the bug where the export crashed when a name was empty
Output:
```
fix(export): skip rows with empty names

CSV export raised KeyError on rows without a name field. Skip them and
log a warning so the rest of the export still completes.

Closes #214
```

## Branch names
`<type>/<short-kebab-description>`, with the issue number when one exists: `fix/123-login-timeout`, `feat/export-csv`.

## PR description
Use the repo's template if it has one; otherwise:

```
## Summary
One or two sentences: what this does and why.

## Changes
- Notable changes, grouped logically

## How to test
1. Steps a reviewer can follow
2. Expected result

## Notes for reviewers
Risky areas, trade-offs, follow-ups, and what is deliberately not included.

## Related
Closes #<issue>
```

Keep a PR small enough to review in one sitting; if it is larger, propose a split. Include screenshots or output for UI or behavior changes.

## Reviewing a PR
Review in this order, since earlier items cost more if missed:

1. Correctness: logic errors, edge cases, race conditions, error handling.
2. Security: input validation, secrets, injection, permissions.
3. Design: fit with the architecture, needless complexity.
4. Tests: meaningful coverage of new behavior and edge cases.
5. Readability: naming, comments on the non-obvious, dead code.
6. Style: only what the linter does not already catch.

Prefix each comment with `blocking:`, `suggestion:`, `question:` or `nit:` so the author knows what must change. Be specific, give the reason, propose a fix, note what is done well, and critique the code, not the person.

## Resolving conflicts
1. Fetch the latest base branch.
2. Merge or rebase per repo convention (ask if unknown).
3. Understand the intent of *both* sides before choosing; picking one blindly loses work.
4. Run tests or the build.
5. Summarize what was resolved and any judgment calls.
