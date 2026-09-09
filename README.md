# Agent docs templates

Copy these into a new repo and fill the brackets. Headings stay; replace the
short descriptions with your project facts.

```
AGENTS.md                         # always-on operating file
CLAUDE.md                         # Claude Code import of AGENTS.md
scope.md                          # living build journal
context/
  project-overview.md             # product the agent must not invent
  architecture.md                 # boundaries and invariants
  code-standards.md               # repo-unique rules
  ui-context.md                   # tokens and UI do-nots
  progress-tracker.md             # done / next
  feature-spec.md                 # copy once per unit of work
examples/
  nested-AGENTS.md                # optional, next to one dangerous folder
```

Do not add a root `context.md`. Product context lives only under `context/`.

1. Copy `AGENTS.md` and `CLAUDE.md` to the repo root.
2. Copy the `context/` folder.
3. Copy `scope.md`.
4. Fill product, stack, commands, and in/out of scope before the first agent session.
5. Copy `examples/nested-AGENTS.md` into a folder only when that folder has a load-bearing gotcha.
