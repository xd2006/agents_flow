# ONBOARDING_SKILL

## Trigger
After a new agent has been installed.

## Procedure
1. Create `Agent_Memory/<Agent_ID>/` if missing.
2. Create missing files only: `MEMORY.md`, `WORK_LOG.md`, `DECISION_LOG.md`, `OPEN_QUESTIONS.md`, and `tasks/`.
3. Seed `MEMORY.md` with agent identity, role, runtime, source package, and links to relevant shared files; do not copy secrets or assume unverified access.
4. Add registry entry and relationships declared in the package. If relationships are ambiguous, register the agent with no inferred links and list questions.
5. Update `_Shared/ARTIFACT_INDEX.md` and `PROJECT_STATE.md` only if relevant.
6. Record what the agent can actually read/write and what is merely requested in its prompt.
7. Write an onboarding summary. Existing agents learn about the new participant by reading shared registry/context on their next task; direct notifications require a real messaging capability.
