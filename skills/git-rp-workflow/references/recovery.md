# Recovery Playbook

When something goes wrong, stop and understand the state before running more commands: extra commands on a confusing state are how small mistakes become lost work. Run `git status` and `git reflog` first, and explain what a recovery command does before running it.

| Situation | Approach |
|---|---|
| Committed to the wrong branch | Create the right branch at the current commit, then move the original branch back (confirm first) |
| Undo a pushed commit | `git revert <sha>`, which is safe for shared history |
| Undo last local commit, keep changes | `git reset --soft HEAD~1` |
| Lost commits after reset or rebase | `git reflog`, find the SHA, `git branch rescue <sha>` |
| Accidentally staged files | `git restore --staged <file>` |
| Secret was committed | Rotate the secret first, then discuss a history rewrite with the user |
| Messy merge in progress | `git merge --abort` returns to the pre-merge state |
| Messy rebase in progress | `git rebase --abort` |
| Discarded changes by accident | Check `git stash list` and `git fsck --lost-found`; uncommitted work may be unrecoverable, so say so honestly |
