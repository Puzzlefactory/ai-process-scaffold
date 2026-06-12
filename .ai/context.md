# Project Context

## Goal

Create a lightweight, reusable process scaffold for development projects that use coding agents. The scaffold should help agents find the right context, preserve durable state across sessions, and avoid unnecessary process overhead.

## Current Shape

The repo contains root agent entry shims, a canonical `.ai/instructions.md` workflow, rolling context and decisions files, a generic stack template, coordination guidance, risk/review guidance, optional disposable task guidance, workstream templates, prompt templates, and ADR scaffolding. The process model is actively being refined and needs validation in fresh agent sessions.

## Repository Layout

- `AGENTS.md` and `CLAUDE.md`: thin entry points for coding agents
- `.ai/`: durable agent context and workflow files
- `.ai/workstreams/`: current-state files for open-ended or multi-session work
- `.ai/tasks/`: ignored short-lived task files
- `.ai/prompt-templates/`: reusable copy-and-fill prompts for authorizing or coordinating agent work
- `docs/adr/`: place for architecture decision records
- `docs/graphics/`: project-specific brand assets that may not belong in the generic scaffold

## Important Artifacts

- `README.md`
- `.ai/instructions.md`
- `.ai/decisions.md`
- `.ai/stack.md`
- `.ai/tasks/README.md`
- `.ai/workstreams/process-scaffold-refinement.md`

## Current Phase

Refinement and validation. The current focus is making the scaffold agent-friendly, human-adoptable, and generic enough for many development project types.

## Resume Guidance

When resuming work:

1. Read `.ai/decisions.md`.
2. Read the relevant workstream file in `.ai/workstreams/`.
3. Check git status.
4. Continue from the workstream's next actions rather than relying on chat history.
