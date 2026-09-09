# AGENTS.md

Always-on file for Cursor, Codex, Copilot, and Claude Code (via `CLAUDE.md`).
Keep this short. Point at other files; do not paste them in.

**[Product]** — one sentence: who it is for and what it does.

Do not invent product behavior that is not written in `context/` or `scope.md`.

## Index

Read this file every session. Read the other files only when the task needs them.

| File | Read when |
| --- | --- |
| `context/project-overview.md` | New feature, scope question, or anything user-facing |
| `context/architecture.md` | New folder, API, data model, or auth change |
| `context/code-standards.md` | Writing or reviewing code |
| `context/ui-context.md` | UI / CSS / components |
| `scope.md` | Continuing a slice, claiming status, or changing a decision |
| `context/progress-tracker.md` | Starting or ending a unit of work |
| Nested `AGENTS.md` | Editing that folder. Write nested files as deltas; Cursor combines them with this file, other tools may let the closest file win. |

## Work loop

Skip the pause when the change is a one-line or one-file fix.

1. Inspect existing code. Do not assume shape from training data.
2. Ask one focused question only if the task is genuinely ambiguous. Offer two or three options.
3. For a new slice or a boundary crossing: write a few sentences of intent, then wait for approval unless the user said to skip.
4. Implement only that unit. Do not overbuild.
5. Run the commands below. Never claim a check passed without running it.
6. Update `scope.md` and `context/progress-tracker.md`.
7. Reply with: `What I did` · `Test` · `Needs your attention`.

## Fences

- Build only what the current unit and `scope.md` ask for.
- Do not invent features, endpoints, or UI states that are not specified.
- Do not modify generated foundation files unless the task says to.
- If a requirement is missing, add it as an open question in `context/progress-tracker.md` before coding.

## Stack

Fill once. Do not add a second framework, auth provider, or data store without updating `context/architecture.md`.

| Layer | Technology | Role |
| --- | --- | --- |
| Framework |  |  |
| Auth |  |  |
| Database |  |  |
| AI |  |  |
| Styling |  |  |

## Skills

Use listed skills (or `.agents/skills/` / `.claude/skills/`) before guessing an SDK. Do not invent new skills.

- _(name — path)_

## Commands

Exact strings, from repo root.

- Typecheck:
- Lint:
- Production build:
- Dev server:
- Tests: _(or `none — verify manually`)_

## Secrets and boundaries

- Canonical env list: `.env.example`
- Browser may only see values meant for the client
- Server-only: service-role keys, provider API keys, admin secrets
- UI displays stored data. It does not scrape, call models, or mutate pipelines.

## Nested AGENTS.md

List them here as you add them:

- _(path — one-line why)_
