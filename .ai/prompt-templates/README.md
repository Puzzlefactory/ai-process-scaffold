# Prompt Templates

Reusable prompts for authorizing or coordinating agent work.

Fill in the placeholders, keep the authorization scoped, and let `AGENTS.md` and `.ai/instructions.md` remain the source of truth for repo workflow.

## Prompt Template Rule

Prompt generation is user-triggered. When the user asks for a prompt to authorize agent work, always generate it from one of the templates in this directory.

Do not invent a new prompt structure unless the user explicitly asks for a custom format.

## Templates

- `work-authorization-light.md`: authorize small, bounded work where scope, verification, and closeout are enough.
- `work-authorization-medium.md`: authorize planned work with constraints, expected checks, or review needs without the full process wrapper.
- `work-authorization.md`: authorize substantial planning outcomes, high-risk work, workstreams, or feature work from startup through closeout.

## Choosing A Template

Use the light template for a clear one-session change.

Use the medium template when the work has meaningful constraints, tradeoffs, or review expectations but does not need full research and durable-context handling up front.

Use the full template after substantial planning, or when the work should proceed end to end with explicit research, review, task-file decision, durable context, and closeout.

Independent review does not imply a task file. Task files are only for durable execution state, multi-agent coordination, resumable work, blocked or paused work, or explicit authorization.
