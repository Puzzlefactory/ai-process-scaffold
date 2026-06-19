# Workstream: Process Scaffold Refinement

Status: active
Created: 2026-05-27
Last Updated: 2026-06-19

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

The scaffold has thin root entry files, a conditional startup flow in `.ai/instructions.md`, and
three prompt templates tiered by risk. Startup now requires agents to check git status and read
`context.md`/`decisions.md` only for non-trivial or ambiguous tasks — not unconditionally.
`context.md` has been trimmed to current state and resume pointers only; repository layout content
was removed (it belongs in `README.md`). The `context/` archive pattern is now codified with a
`README.md` naming convention and a `LATEST.md` pointer. `instructions.md` references
`coordination.md` explicitly on high-risk work so agents know to check it. The three prompt
templates have been tightened — the medium variant no longer duplicates full-template preamble.
`docs/graphics/` has been removed (contained project-specific brand assets by mistake).

## Next Actions

- Test the updated scaffold with at least one fresh agent session and note where it follows or ignores the flow.
- Validate whether conditional startup reads cause agents to skip context they actually need.
- Consider propagating lean-startup improvements back to `le-mono-repo-1` which is still on the older mandatory-reads pattern.
- Keep root wrappers minimal unless evidence shows a specific agent needs an additional startup guard.

## Completion Shape

This workstream is substantially complete when:

- Root entry files are minimal and stable.
- A human README gives adopters a clear starting point.
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
- **Human README:** The repo needs a root `README.md` for adopters; agent entry files are not a substitute for human onboarding.
- **Branch cleanup timing:** The current work will be merged into `main`; after the merge, the `initial-design` branch will be deleted.
- **Conditional linked-file reads:** Agents should always read required startup files, then read stack, coordination, task, and workstream files only when the selected flow calls for them.
- **Risk/review separation:** Risk level controls review rigor; coordination need controls whether a disposable task file is useful.
- **Verified missing-file claims:** Agents must inspect the filesystem before reporting that referenced `.ai` files are missing.

## Key Files

- `AGENTS.md`
- `CLAUDE.md`
- `README.md`
- `.ai/instructions.md`
- `.ai/context.md`
- `.ai/decisions.md`
- `.ai/stack.md`
- `.ai/tasks/README.md`
- `.ai/prompt-templates/work-authorization.md`
- `.ai/workstreams/README.md`
