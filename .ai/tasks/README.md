# Task Files And Review

Task files are short-lived execution plans for specific work. They are not durable project history.

Risk level controls review rigor. Coordination need controls whether a task file is useful.

Durable state belongs in:

- `.ai/workstreams/`
- `.ai/context.md`
- `.ai/decisions.md`
- `docs/adr/`

## Lifecycle Rule

A task is complete only when:

- the work is completed or explicitly abandoned
- required review is completed or explicitly waived
- durable findings are copied into the relevant workstream, context, decisions, stack notes, or ADR when needed
- the task file is deleted

Active task files are ignored by git. Do not commit them.

## Risk Levels

### High Risk

High-risk or broad work.

Examples:

- auth/session architecture
- shared API/runtime package changes
- validator behavior changes with broad impact
- cross-feature or cross-package refactors
- changes that alter the process contract

Requirements:

- independent review is required unless the user explicitly waives it
- if required independent review is unavailable, state exactly why, perform an explicit self-review, and report that fallback in closeout
- durable context update required when project state, decisions, or next actions change

### Medium Risk

Moderate-risk, bounded work.

Examples:

- feature-level behavior changes
- prompt/template changes that affect future Make output
- package API additions with limited scope
- updates to experiment packs or review checklists

Requirements:

- independent review is required for source-of-truth data/storage, API contracts, auth/security, pipelines, build/deploy tooling, process contracts, broad UI behavior, or user-specified review boundaries
- independent review is preferred for other medium-risk work
- if required independent review is unavailable, state exactly why, perform an explicit self-review, and report that fallback in closeout
- durable context update required when project state, decisions, or next actions change

### Low Risk

Low-risk, isolated work.

Examples:

- typo fixes
- small wording edits
- read-only analysis
- local inspection
- narrow documentation clarification

Requirements:

- self-review is allowed
- update durable context only if the current state changes

## Task File Triggers

For single-session contained work, no task file is needed — the agent manages execution state
internally. Create a task file only when the state needs to be visible outside the agent:

- multi-agent coordination
- long-running or resumable work
- work paused before completion
- explicit user authorization requiring a task file

A task file appearing in `.ai/tasks/` signals that something is in flight or needs handoff.

## Task Template

```md
# Task: <short name>

## Risk

High | Medium | Low

Why this risk level applies.

## Coordination

Why this task file is needed.

## Scope

What will change, and what is explicitly out of scope.

## Plan

- [ ] Step 1
- [ ] Step 2
- [ ] Step 3

## Review Requirement

- Required: yes | no
- Reviewer:
- Result:

## Verification

- [ ] Commands/checks run, or reason they were not run

## Closeout Requirements

- [ ] Work completed or explicitly abandoned
- [ ] Required review completed or waived
- [ ] Durable findings copied to the relevant `.ai` file when needed
- [ ] Task file deleted
```
