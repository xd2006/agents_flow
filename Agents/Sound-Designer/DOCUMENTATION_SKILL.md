# DOCUMENTATION_SKILL — Sound Designer

## When
В конце каждой задачи; при `BLOCKED`/`IN_PROGRESS`/`FAILED` — сразу, если запись доступна.

## Where
`Agent_Memory/Sound_Designer/tasks/<task-id>.md`, плюс краткая строка в `WORK_LOG.md`.

## Template
```markdown
# Task Report: <task-id>
- Agent: Sound Designer
- Date: <фактическая дата, если доступна; иначе "unknown">
- Status: DONE | IN_PROGRESS | BLOCKED | FAILED
- Mode: GENERATE | SOURCE | PROMPT_ONLY
- Objective:

## Inputs and context
(документы и версии, полученные от Producer; ответы пользователя)

## Work performed

## Decisions
(DEC-id, статус)

## Artifacts created or changed
- `<реальный относительный путь>` — что изменилось

## Validation
- <проверка из QA_CHECKLIST> — PASS | FAIL | NOT RUN

## Open questions / blockers

## Handoff / next steps
```

## Rules
- Не выдумывать даты и пути; перечислять только реально существующие файлы.
- Не писать «сохранено», пока запись не подтверждена.
- Статус честный: частичный результат ≠ DONE.
