# Track B: Roleplay (RP) Repositories

Treat the repo as a living story bible with full history: git gives you undo, branching timelines and a record of who established which fact.

## Contents
- Suggested structure
- Character file template
- Session logs and scenes
- Canon consistency
- Git practices for RP
- Writing in character

## Suggested structure
```
characters/   one file per character (mira.md)
world/        locations, factions, rules of magic or tech, timeline
scenes/       polished scenes, numbered (012-harbor-confrontation.md)
sessions/     raw logs, dated (2026-10-10-session-03.md)
canon/        facts.md and a contradictions log
threads/      open plot threads and hooks
README.md     premise, tone, content boundaries, how to contribute
```
Adapt to what exists, and ask before restructuring.

## Character file template
```
# <Name>
**Role:** | **Age:** | **Affiliation:**
## Concept (one line)
## Appearance
## Voice (speech rhythm, verbal habits, what they never say)
## Desire / Need / Flaw
## Secrets (mark SPOILER if the repo is shared)
## Relationships
## Arc so far (dated entries, newest last)
```

## Session logs and scenes
- Keep raw logs unedited in `sessions/` and polished versions separately in `scenes/`, so the original is never lost.
- Date every entry and use consistent speaker labels.
- After each session add a summary: what happened, what changed for each character, new facts, new open threads.

## Canon consistency
- `canon/facts.md` holds one line per established fact with its source (session or scene).
- Check new material against canon and character files before writing it. On a conflict, flag it and offer options: retcon, in-world explanation, or unreliable narration. Silent changes to established facts break trust with co-authors.
- Track in-world timeline order separately from writing order.

## Git practices for RP

**Commits** act as narrative checkpoints.
- `scene: 012 the harbor confrontation`
- `char(mira): add backstory entry`
- `canon: record bridge collapse (session 04)`

**Branches** hold what-ifs and drafts: `alt/mira-survives`, `draft/act-two-rewrite`. Merge only when the author adopts the branch as canon.

**Tags** mark milestones: `arc-1-complete`, `session-10`.

**Multiple authors:** change canon through PRs so co-authors can review, and keep private character secrets in clearly marked files.

**Content boundaries:** follow the README. If none exist and material turns mature or sensitive, check the user's preferences first. Never write sexual content involving minors.

## Writing in character
Apply the voice notes in the character file. Keep each character's speech distinct, convey emotion through action and subtext, and avoid stock phrases. Do not decide the user's own character's actions or inner thoughts unless asked.
