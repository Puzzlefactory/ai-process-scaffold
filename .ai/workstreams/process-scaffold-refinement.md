# Workstream: Process Scaffold Refinement

Status: active
Created: 2026-05-27
Last Updated: 2026-05-27

This workstream tracks refinement of the reusable agent process scaffold. The goal is to make the workflow small, clear, and reliable enough that different coding agents can follow it across many project types without over-reading, skipping required context, or inventing missing files.

## Scope

In scope:
- Entry-point behavior for `AGENTS.md`, `CLAUDE.md`, and similar agent wrappers
- The canonical workflow in `.ai/instructions.md`
- Criteria for when agents read stack, coordination, task, and workstream files
- Workstream and task-file ergonomics
- Evidence from real agent runs using the scaffold

Out of scope:
- Project-specific implementation guidance for downstream repos
- Tool-specific prompt engineering that does not belong in the shared scaffold
- Large policy documents that make startup heavy

## Current State

The scaffold now uses thin root entry files that point agents to `.ai/instructions.md`. The instructions file contains a small required startup, task-type workflow branches, conditional reads for linked files, and a guard against claiming `.ai` files are missing without a filesystem check. `.ai/stack.md` has been generalized so it can describe many kinds of development projects, not only design systems.

## Next Actions

- Test the updated scaffold with at least one fresh agent session and note where it follows or ignores the flow.
- Decide whether `.ai/tasks/README.md` is too heavy for common projects or whether the tier system should remain as-is.
- Consider adding a short checklist for agent closeout if repeated sessions fail to update durable context.
- Keep root wrappers minimal unless evidence shows a specific agent needs an additional startup guard.

## Completion Shape

This workstream is substantially complete when:

- Root entry files are minimal and stable.
- `.ai/instructions.md` is short enough for agents to follow but explicit enough to prevent common failure modes.
- The stack, coordination, task, and workstream files have clear conditional triggers.
- The scaffold has been tested in at least two agent environments or sessions.
- Open process questions are resolved or moved to decisions.

## Blockers / Constraints

- Different agents may ignore or reinterpret instructions unless the first steps are concrete and easy to verify.
- The scaffold must stay generic enough for many project types.
- Process files should remain small; agent-friendly brevity is a design constraint.

## Key Decisions

- **Thin root wrappers:** `AGENTS.md` and `CLAUDE.md` should point to `.ai/instructions.md` instead of duplicating the full file list.
- **Conditional linked-file reads:** Agents should always read required startup files, then read stack, coordination, task, and workstream files only when the selected flow calls for them.
- **Verified missing-file claims:** Agents must inspect the filesystem before reporting that referenced `.ai` files are missing.

## Key Files

- `AGENTS.md`
- `CLAUDE.md`
- `.ai/instructions.md`
- `.ai/context.md`
- `.ai/decisions.md`
- `.ai/stack.md`
- `.ai/tasks/README.md`
- `.ai/workstreams/README.md`
