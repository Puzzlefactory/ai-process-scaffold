# Patterns

## When to Spawn an Agent

Spawn when:

- Research or exploration spans the codebase broadly (more than 3 targeted lookups)
- Work can run in parallel with other independent work
- Large search results or deep exploration would pollute the main context window
- The task matches a specialized agent type (Explore, Plan, etc.)

Do the work inline when:

- You already have the relevant context from earlier in the session
- The task is contained enough to complete in a few tool calls
- You need the result immediately to determine your next step

## Briefing a Spawned Agent

Spawned agents start cold — no memory of this conversation, no awareness of what has been tried. The prompt must be self-contained.

A good brief includes:

- What you are trying to accomplish and why
- What has already been tried or ruled out
- Relevant file paths, line numbers, or symbols
- What form the result should take

Never delegate understanding. A prompt like "based on your findings, fix the bug" pushes synthesis onto an agent that lacks the context to do it well. Write the brief to prove you understood the problem first — the agent executes, it does not reason from scratch.

When spawning agents in parallel, each needs a fully self-contained prompt and a disjoint write scope. Two agents writing to the same file will conflict.

## Roles

- **Orchestrator** — scopes the work, assigns agents, coordinates review, handles closeout. The main session is the orchestrator.
- **Owner** — implements within the agreed scope. Receives a self-contained brief from the orchestrator.
- **Reviewer** — a freshly spawned agent with no context from the implementation session. Brief it with the scope, the changed files, and what to look for. If spawning fails, self-review explicitly and report the fallback in closeout.

For low-risk work, one agent may act as both orchestrator and owner.

## Review Assignment

- High risk: independent review is required unless the user explicitly waives it.
- Medium risk: independent review is required for source-of-truth data/storage, API contracts, auth/security, pipelines, build/deploy tooling, process contracts, broad UI behavior, or user-specified review boundaries.
- Other medium-risk work: independent review is preferred.
- Low risk: self-review is allowed.
- If required independent review is unavailable, state exactly why, perform an explicit self-review, and report that fallback in closeout.
- The owner must not act as the reviewer when independent review is required.

## When to Surface to the User

Interrupt for:

- blockers
- approval boundaries
- meaningful tradeoffs
- review findings that require a decision or rework

Do not interrupt for routine steps — tool calls, file reads, intermediate results, task cleanup. The orchestrator absorbs these.
