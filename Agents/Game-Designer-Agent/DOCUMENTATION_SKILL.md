# Mandatory Skill: Documentation

## Trigger
At the end of every task, including blocked or partially completed tasks.

## Procedure
1. Identify the task and its final status: `DONE`, `IN_PROGRESS`, `BLOCKED`, or `FAILED`.
2. Record objective, relevant inputs, work performed, artifacts created/changed, validation performed, decisions, open questions, blockers, and next steps.
3. Save a detailed report as `Agent_Memory/Game_Designer/tasks/<task-id>.md` when filesystem access exists.
4. Update `WORK_LOG.md` with a concise chronological entry and links to reports.
5. Update `MEMORY.md` only with durable, reusable context; do not copy the entire task transcript into long-term memory.
6. Confirm paths and writes through the available runtime. If writing is unavailable, provide content and intended paths without claiming persistence.

## Required task report
Use `templates/TASK_REPORT_TEMPLATE.md`. Include actual date/time only when available; never invent IDs, timestamps, file paths, test results, or approvals.
