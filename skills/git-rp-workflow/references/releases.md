# Track C: Release & Repo Management

## Contents
- Versioning
- Release checklist
- Changelog format
- Branching strategies
- Housekeeping

## Versioning
Semantic Versioning (`MAJOR.MINOR.PATCH`) unless the repo says otherwise:
- MAJOR: incompatible changes
- MINOR: backward-compatible features
- PATCH: backward-compatible fixes

Content or RP repos can use a lighter scheme (`arc-N`, `session-N`, or date tags).

## Release checklist
1. Working tree clean, on the correct branch, up to date with the remote.
2. Tests and build pass, if any exist.
3. Choose the next version from the changes since the last tag: `git log <last-tag>..HEAD --oneline`.
4. Update the changelog and any version fields.
5. Commit: `chore(release): vX.Y.Z`.
6. Annotated tag: `git tag -a vX.Y.Z -m "Release vX.Y.Z"`.
7. Ask before pushing the commit and tag, since tags are hard to retract once others fetch them.
8. Draft release notes.

## Changelog format (Keep a Changelog style)
```
## [X.Y.Z] - YYYY-MM-DD
### Added
### Changed
### Deprecated
### Removed
### Fixed
### Security
```
Write entries for readers: describe the effect, not the commit message, and link PRs or issues.

**Example**
Input commit: `fix(export): skip rows with empty names`
Entry: "Fixed: CSV export no longer fails when a row has no name (#214)."

## Branching strategies
- **Trunk-based** (default for small teams or solo): short-lived branches off `main`, merged often.
- **Git Flow** (`main`, `develop`, `feature/`, `release/`, `hotfix/`): only when the project truly ships staged releases.
- Delete merged branches and protect `main`.

## Housekeeping
Keep a sensible `.gitignore`, a useful README and a `LICENSE`. List stale branches and confirm with the user before pruning.
