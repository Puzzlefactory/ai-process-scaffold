# Light Work Authorization

Proceed with `<small bounded change>`.

## Scope

In scope:

- `<specific change>`

Out of scope:

- `<thing not authorized>`

## Risk And Coordination

Expected risk: `Low`.

Expected task file: `no`.

Do not create a task file unless this work becomes resumable, multi-agent, blocked before completion, or explicitly requires durable execution state.

## Implementation

Read `AGENTS.md`, then follow the startup and task flow in `.ai/instructions.md`.

Make the scoped change without unrelated refactors or package additions.

## Verification

Run the relevant lightweight check for this change.

Report commands run and any failures.

## Review

Self-review is sufficient unless the actual risk is higher than expected.

If the risk changes, follow the review requirements in `.ai/tasks/README.md`.

## Closeout

Summarize changed files.

Confirm no task file was required, or confirm any created task file was deleted.

Confirm durable `.ai` context was updated, or state that no durable context update was needed.
