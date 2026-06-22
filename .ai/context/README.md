# Context Archive

Dated records of reasoning, findings, and session handoffs that have cross-session value but do not
belong in a workstream or `decisions.md`. Decisions belong in `decisions.md` or `docs/adr/` —
not here.

## When to Write a Record

Write a context record when a session produces reasoning or findings that future agents will need
to understand why the project is in its current state.

Do not write records for routine progress, completed single-session tasks, or information already
captured in a workstream, `decisions.md`, or `stack.md`.

## Naming Convention

```
YYYY-MM-DD-HHMM-short-slug-describing-the-session.md
```

Example: `2026-06-19-1430-lean-startup-refinement.md`

Use 24-hour time. The slug should be specific enough to identify the record without opening it.

## Index Maintenance

After adding a record, update `LATEST.md` with the new filename and date. That pointer is the
fast path for agents resuming a thread — they read `LATEST.md` rather than scanning this directory.

## Index

<!-- Add entries here as records are created, most recent first -->
