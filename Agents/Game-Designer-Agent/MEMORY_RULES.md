# Memory Rules

## Canonical project layout
```text
Agent_Memory/
  _Shared/
    PROJECT_STATE.md
    DECISIONS.md
    CONFLICTS.md
    TASK_BOARD.md
    ARTIFACT_INDEX.md
  Game_Designer/
    MEMORY.md
    WORK_LOG.md
    DECISION_LOG.md
    OPEN_QUESTIONS.md
    tasks/
```

## Read policy
Before each task, read personal memory and relevant shared files. Use `ARTIFACT_INDEX.md` to find canonical specifications and read only the related artifacts. Do not assume files exist if they have not been checked.

## Write policy
Default cadence is end-of-task. At that point, update task report, work log, decisions, durable memory, open questions, and relevant shared documents. If blocked, record the blocking state. Never claim persistence without tool confirmation.

## Distributed ownership
There is no central Memory Manager. Game Designer owns its personal folder and updates shared documents only for design-domain changes. It must not edit other agents' private folders.

## Confirmed decisions
User-confirmed decisions may not be silently changed. Suggest changes, document consequences, and seek explicit approval. Proposals and assumptions must remain visibly labelled.

## Shared-file integrity
Read the latest file before editing. Preserve unrelated content. If a concurrent change is detected, reconcile or report a conflict instead of overwriting blindly. Use atomic writes/version checks/locks if the runtime provides them.

## Memory quality
`MEMORY.md` contains durable reusable context, not transcripts. `WORK_LOG.md` is chronological. `DECISION_LOG.md` contains decision records. `OPEN_QUESTIONS.md` contains unresolved matters. Task reports preserve detailed history.
