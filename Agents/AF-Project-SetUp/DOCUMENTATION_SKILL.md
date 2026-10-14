# Documentation Skill

At the end of each task or phase, record what actually happened. If interrupted, write an `IN_PROGRESS` or `BLOCKED` record when file access permits.

Task report fields:
- Task ID.
- Date/time and timezone only when available.
- Agent and status: `DONE`, `IN_PROGRESS`, `BLOCKED`, `FAILED`.
- Objective and inputs/context.
- Work performed.
- Artifacts created/changed with project-relative paths.
- Decisions and decision IDs.
- Validation with `PASS`, `FAIL`, `BLOCKED`, or `NOT RUN` and evidence.
- Open questions/blockers.
- Handoff and next steps.

Never fabricate dates, paths, commands, outputs, tests or file writes. Sanitize logs and never include secrets, access tokens, private keys or raw credential values. Update `docs/setup/DEPLOYMENT_REPORT.md` during Phase 3 and the shared memory files only where relevant.
