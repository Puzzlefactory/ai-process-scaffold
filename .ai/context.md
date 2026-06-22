# Project Context

## Goal

Create a lightweight, reusable process scaffold for development projects that use coding agents. The scaffold should help agents find the right context, preserve durable state across sessions, and avoid unnecessary process overhead.

## Current Shape

The repo contains root agent entry shims, a canonical `.ai/instructions.md` workflow, rolling context and decisions files, a generic stack template, coordination guidance, risk/review guidance, optional disposable task guidance, workstream templates, prompt templates, and ADR scaffolding. The process model is actively being refined and needs validation in fresh agent sessions.

## Current Phase

Refinement and validation. The current focus is making the scaffold agent-friendly,
human-adoptable, and generic enough for many development project types.

## Active Workstreams

- [Process Scaffold Refinement](.ai/workstreams/process-scaffold-refinement.md)

## Resume Guidance

When resuming work:

1. Check git status.
2. Read `.ai/decisions.md`.
3. Read `.ai/context/LATEST.md` — if it points to a real record, read that record.
4. Read the relevant workstream file in `.ai/workstreams/`.
5. Continue from the workstream's next actions rather than relying on chat history.
