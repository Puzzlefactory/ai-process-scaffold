# Durable Decisions

This file is a rolling index of currently binding decisions. Use ADRs in `docs/adr/` for full rationale when a decision needs more context.

## Active Decisions

- `.ai/` is the committed durable context area for cross-agent instructions, rolling project context, decisions, and active workstreams.
- `context.md` and `decisions.md` are rolling current-state files, not dated archives. `context.md` holds current phase, active workstream pointers, and resume guidance only — not repository layout or structural descriptions.
- Use workstream files for active flow state; workstreams are updated in-place, not appended.
- Use ADRs for significant process or architecture decisions.
- Startup reads are conditional: agents check git status always; read `context.md` and `decisions.md` only when the task is non-trivial, architectural, resumed, or ambiguous.
- Risk level controls review rigor; coordination need controls whether a disposable task file is useful.
- High-risk work requires independent review unless explicitly waived; required-review fallbacks must state exactly why independent review was unavailable and report explicit self-review. On high-risk work, agents read `.ai/coordination.md` for role definitions and review assignment rules.
- Active task files live under `.ai/tasks/`, are ignored by git, and are used only when execution state needs to survive outside the active agent session.
- Reusable copy-and-fill prompts for authorizing or coordinating agent work live under `.ai/prompt-templates/`.
- Root agent entry files are thin shims; `.ai/instructions.md` owns the workflow and decides which linked files are read for each task type.
- `README.md` is the human onboarding entry point; agent entry files should stay focused on agent startup.
- Dated context records live in `.ai/context/`. Name them `YYYY-MM-DD-HHMM-short-slug.md`. Maintain `LATEST.md` as a fast-path pointer to the most recent record.

## Superseded Decisions

- None yet.
