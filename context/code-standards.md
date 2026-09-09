# Code Standards

Repo-unique rules that survive a session. Prefer a junior-readable function over a clever abstraction.
Delete any bullet the linter already enforces.

## Engineering mindset

- Read context files before assuming.
- Only the current unit.
- If it cannot be verified immediately after, it is incomplete.
- One thing at a time.

## Language and types

Fill with what is unique here (for example: no `any`, env only through one module).

-

## Framework conventions

Replace if you are not on this framework.

-

## File and folder naming

- Folders:
- Components:
- Utils:
- Barrels: client files must not import a barrel that re-exports server-only modules.

## Error handling

- Never show a raw exception or provider error to the user. Plain sentence plus a retry. Real error goes to the server log.
- Fail fast on missing env at boot.

## Machine vs human

**Lint / format already catch:**

-

**Review-only (no honest lint rule):**

- If the same utility classes show up in three places, extract a component.
- If code contradicts `context/architecture.md`, fix the doc too.

## Comments

- Comment only when the why is not in the types.
- Out-of-scope TODOs go in `scope.md`, not in the code.
