# AI Process Scaffold

A small, reusable process scaffold for software projects that use coding agents.

The goal is to give agents enough durable context to work across sessions without turning the repo into a process-heavy documentation system.

## What This Provides

- Thin agent entry files: `AGENTS.md` and `CLAUDE.md`
- A canonical agent workflow: `.ai/instructions.md`
- Rolling project context: `.ai/context.md`
- Active decisions: `.ai/decisions.md`
- Technical baseline: `.ai/stack.md`
- Multi-session work tracking: `.ai/workstreams/`
- Disposable task plans: `.ai/tasks/`
- Reusable agent prompt templates: `.ai/prompt-templates/`
- ADR home: `docs/adr/`

## How To Use It In A Project

1. Copy `AGENTS.md`, `CLAUDE.md`, `.ai/`, and `docs/adr/` into the target repo.
2. Fill in `.ai/context.md` first.
3. Fill in `.ai/stack.md` when the project has real technical choices.
4. Keep `.ai/decisions.md` as the current index of binding decisions.
5. Create workstreams only for open-ended, multi-session, architectural, or cross-agent work.
6. Leave `.ai/tasks/` empty except for short-lived active task files.
7. Use `.ai/prompt-templates/` as optional copy-and-fill prompts for authorizing or coordinating agent work.

## What To Customize First

Start with these files:

- `.ai/context.md`: project goal, current shape, important files, and resume guidance
- `.ai/stack.md`: runtime, architecture, interfaces, storage, deployment, and quality gates
- `.ai/decisions.md`: decisions that future agents must preserve

Then remove or close any scaffold-development workstreams that do not apply to the target project.

## About The Process Workstream

This repo includes `.ai/workstreams/process-scaffold-refinement.md` because this scaffold is still being refined.

When adopting the scaffold into another project:

- Keep it only if you want to continue improving the scaffold inside that repo.
- Delete it if the downstream project only needs the process files.
- Replace it with project-specific workstreams when real ongoing work begins.

## Updating An Existing Project

When this scaffold improves later, do not blindly overwrite a downstream repo.

1. Compare `AGENTS.md`, `CLAUDE.md`, and `.ai/instructions.md`.
2. Bring over process changes that improve agent behavior.
3. Preserve project-specific context, decisions, stack notes, and workstreams.
4. Record meaningful process changes in `.ai/decisions.md` or a project ADR.

## Current Cleanup Notes

- The scaffold still needs validation in fresh agent sessions.
- The task tier system may need simplification after real use.
- `docs/graphics/` contains project-specific brand assets and should be removed if this repo is intended to stay fully generic.

## Design Principles

- Keep startup small enough that agents actually follow it.
- Store durable state in files, not chat history.
- Prefer current state over append-only logs.
- Read linked files only when the task flow calls for them.
- Verify files with the filesystem before claiming they are missing.
