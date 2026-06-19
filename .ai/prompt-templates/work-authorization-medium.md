# Medium Work Authorization

Proceed with `<planned change>` end to end.

## Scope

In scope:

- `<specific change 1>`
- `<specific change 2>`

Out of scope:

- `<thing not authorized>`
- `<thing not authorized>`

## Risk And Coordination

Expected risk: `Medium`.

Expected task file: `no`.

If the classification differs from the expected risk, follow the actual review requirements and
mention the reason in closeout.

Create a task file only if coordination requires durable execution state, the work becomes
resumable, multiple agents are involved, the work is blocked before completion, or this
authorization explicitly requires one.

## Constraints

- `<constraint 1>`
- `<constraint 2>`

## Implementation

Read `AGENTS.md`, then follow the startup and task flow in `.ai/instructions.md`.

Make the authorized changes. Keep changes scoped to this authorization.

Do not implement out-of-scope packages, apps, features, or refactors.

## Review

Independent review is preferred for medium-risk work, and required when the actual risk or user
authorization requires it.

If required independent review cannot be performed, state exactly why, do an explicit self-review,
and report that fallback in closeout.

## Verification

Run relevant tests, builds, typechecks, smoke checks, or visual checks.

Report commands run and any failures.

## Closeout

Summarize changed files and important decisions.

Confirm no task file was required, or confirm any created task file was deleted.

Confirm durable `.ai` context was updated, or state that no durable context update was needed.

Interrupt only if completing this task requires changing something outside the authorized scope, or
if you discover that the authorized approach is unsafe or blocked. Do not interrupt for
implementation choices within scope.
