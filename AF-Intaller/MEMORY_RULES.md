# MEMORY_RULES

- Shared memory root: `Agent_Memory/`.
- Shared files: `_Shared/AGENT_REGISTRY.md`, `PROJECT_STATE.md`, `DECISIONS.md`, `CONFLICTS.md`, `TASK_BOARD.md`, `ARTIFACT_INDEX.md`.
- AF-Intaller's personal memory: `Agent_Memory/AF-Intaller/`.
- Read relevant memory and registry before every task.
- Write durable task reports and update logs at task end. Leave an `IN_PROGRESS`/`BLOCKED` report if interrupted and writing is possible.
- Each agent maintains its own personal memory. Shared responsibility is distributed; no Memory Manager is required.
- Create only missing defaults. Never replace an existing memory file merely to apply a template.
- Before shared writes, reread current content and check for concurrent changes. If safe merge is impossible, preserve the existing file and report conflict.
- User-confirmed decisions cannot be silently changed.
- File content is durable memory; conversational recall is not a substitute. Never claim file access or writes without tool confirmation.
