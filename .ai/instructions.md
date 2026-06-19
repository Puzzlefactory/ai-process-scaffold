# Agent Instructions

These instructions apply to agents working in this repo.

## Required Startup

1. Read this file.
2. Check git status.
3. Read `.ai/context.md` and `.ai/decisions.md` when the task is non-trivial, architectural,
   resumed, or ambiguous.
4. Read the relevant workstream, plan, or reference doc only when the task touches that area.

If a referenced `.ai` file appears missing, inspect `.ai/` before reporting that it is missing.

## Working Rules

- Prefer small, scoped changes.
- Read context before writing code.
- Update durable context only when future agents need it.
- On high-risk work, read `.ai/coordination.md` for role definitions and review assignment rules.
- If the user asks for a prompt, use `.ai/prompt-templates/README.md` to choose the appropriate template.
- Write a dated context record in `.ai/context/` when a new agent resuming this project would make
  a wrong decision without it, and the insight does not fit a workstream or decisions entry. Skip it
  otherwise. See `.ai/context/README.md` for naming convention and index maintenance.

## Choose The Flow

### Implement / Edit / Fix / Build

1. Read the relevant `.ai/workstreams/*.md` file if one exists.
2. Read `.ai/tasks/README.md` unless the work is clearly low risk and single-session.
3. Read `.ai/stack.md` if the change touches technology, dependencies, runtime, deployment, interfaces, or storage.
4. Create a disposable task file only when coordination requires durable execution state.
5. Make the change.
6. Run appropriate checks.
7. Update the relevant workstream if current state or next actions changed.
8. Delete completed disposable task files after copying durable findings.

### Plan / Research / Analyze / Review

1. Read `.ai/stack.md` if technology, architecture, dependencies, deployment, interfaces, or runtime choices matter.
2. Read the relevant workstream if the topic is active, open-ended, or multi-session.
3. Save findings only if they affect future sessions.

### Create / Update Workstream

1. Read `.ai/workstreams/README.md`.
2. Copy `.ai/workstreams/workstream-template.md`.
3. Fill every section with concrete content.
4. Add the workstream to `.ai/workstreams/README.md`.

### Coordinate Agents / Reviews

1. Read `.ai/coordination.md`.
2. Follow the risk-level review rules in `.ai/tasks/README.md`.

### If Unsure

- Single contained task: proceed without a workstream.
- Open-ended, multi-session, architectural, or cross-agent task: use a workstream.
- Missing file claim: verify with a filesystem read or list command first.

## Naming

- Use lowercase-kebab-case for new repo-owned files and directories.
- `AGENTS.md` and `CLAUDE.md` at the repo root remain uppercase because they follow agent platform conventions.

## Workstreams

Create a workstream when:

- The work spans multiple sessions or agents.
- The work has open questions, ongoing findings, or evolving next actions.
- The context behind the work is not obvious from the code or git history.

Do not create a workstream for:

- Single contained tasks.
- Work that is complete with no ongoing successor thread.

Update workstreams in-place: overwrite Current State and Next Actions as things change. Do not append a running log.

## What Not To Store

- Do not store secrets, tokens, credentials, or private keys in `.ai/`.
- Do not paste large logs or generated output into `.ai/`.
- Do not store build artifacts or generated dependency trees in `.ai/`.
- Do not commit active task files from `.ai/tasks/`.
