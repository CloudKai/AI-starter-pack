# Agent docs templates

Copy these into a new repo and fill the brackets. Headings stay; replace the
short descriptions with your project facts.

```
AGENTS.md                         # always-on operating file
CLAUDE.md                         # Claude Code import of AGENTS.md
scope.md                          # glance journal (see scope collision below)
context/
  project-overview.md             # product the agent must not invent
  architecture.md                 # boundaries and invariants
  code-standards.md               # repo-unique rules
  ui-context.md                   # tokens and UI do-nots
  progress-tracker.md             # done / next
  feature-spec.md                 # copy once per unit of work
.agents/skills/                   # JS Mastery workflow skills (MIT)
  LICENSE
  architect/ audit/ check/ debug/ develop/ document/ scope/ sync/ test/
examples/
  nested-AGENTS.md                # optional, next to one dangerous folder
  skill-template/                 # copy this to add a skill
```

Do not add a root `context.md`. Product context lives only under `context/`.

Workflow (JS Mastery). Run only the steps a change needs:

```
idea → /scope → /audit → /architect → /develop → /check verify → /test → /check review → /document → /sync
```

`/debug` anytime something breaks. Bare `/scope` to see where things stand.

## Copy into a repo

1. Copy `AGENTS.md` and `CLAUDE.md` to the repo root.
2. Copy the `context/` folder.
3. Copy `scope.md`.
4. Copy `.agents/skills/` (keep `LICENSE` with the skills).
5. Fill product, stack, commands, and in/out of scope before the first agent session.
6. Copy `examples/nested-AGENTS.md` into a folder only when that folder has a load-bearing gotcha.

## Scope collision

This pack's root `scope.md` is a living glance journal. The JS Mastery `/scope` skill writes `docs/scope/` and treats that folder as the feature list other skills scan.

After copy-paste, pick one source of truth:

- Let `/scope` own `docs/scope/`. Keep root `scope.md` as a short glance file (current status, last completed, next) — not a second feature list.
- Or drop root `scope.md` and point `AGENTS.md` at `docs/scope/` only.

Do not maintain both as sources of truth.

## Add a skill

1. Copy `examples/skill-template/` to `.agents/skills/<name>/`.
2. Rename the folder so it matches the YAML `name` (lowercase, hyphens).
3. Fill `description` (what + when, keywords, max 1024 characters).
4. Write instructions in `SKILL.md`. Put long reference in `references/`, scripts in `scripts/`. Keep `SKILL.md` under ~500 lines.
5. List the skill in `AGENTS.md`.
