# Agent Instructions

These instructions apply to any AI agent or assistant working inside this repository.

## Before implementation

1. Read `docs/context/product.md`.
2. Read `docs/context/tech.md`.
3. Read `docs/context/structure.md`.
4. Check whether there is an existing PRD, RFC, ADR, C4 diagram or Technical Brief in Architect Journey.
5. Do not generate code before `requirements.md` and `tasks.md` are clear enough.
6. If the implementation changes an architectural decision, suggest an ADR update.
7. If the implementation changes system structure, suggest a C4 or structure update.
8. If the implementation changes behavior, update `requirements.md`.
9. If the implementation is completed, update `tasks.md`.

## Working rules

- Prefer small vertical slices over large horizontal changes.
- Keep requirements testable.
- Identify assumptions explicitly.
- Preserve unchanged behavior in bugfixes.
- Do not silently introduce dependencies.
- Do not duplicate architecture documents; reference them.
- When uncertain, write the uncertainty in the spec.

## Output expectations

For a new feature, produce or update:

```text
requirements.md
design.md
tasks.md
traceability.md, if needed
```

For a bugfix, produce or update:

```text
bugfix.md
design.md
tasks.md
regression notes, if needed
```

For an architecture change, produce or update:

```text
design.md
tasks.md
docs-sync-checklist.md
ADR or C4 reference, if needed
```
