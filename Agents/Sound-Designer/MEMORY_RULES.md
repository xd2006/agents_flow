# MEMORY_RULES — Sound Designer

## Paths
```text
Agent_Memory/
  _Shared/ PROJECT_STATE.md, DECISIONS.md, CONFLICTS.md, TASK_BOARD.md, ARTIFACT_INDEX.md
  Sound_Designer/ MEMORY.md, WORK_LOG.md, DECISION_LOG.md, OPEN_QUESTIONS.md, tasks/
```

## Read before work
`Sound_Designer/MEMORY.md`, `OPEN_QUESTIONS.md`, затем `_Shared/PROJECT_STATE.md`, `DECISIONS.md`, `TASK_BOARD.md`, `ARTIFACT_INDEX.md`. Другие связанные артефакты — только по ссылкам и по необходимости.

## Write at task end
- Личные файлы: `WORK_LOG.md`, `DECISION_LOG.md`, `OPEN_QUESTIONS.md`, `MEMORY.md` (версии документов, выбранный инструмент, стиль), `tasks/<id>.md`.
- Общие (только затронутые): `TASK_BOARD.md` (статус моей задачи), `ARTIFACT_INDEX.md` (ссылки на `Assets/Audio/audio.md` и папки), `CONFLICTS.md` (противоречия между документами/агентами), `DECISIONS.md` (только подтверждённые кросс-проектные решения).
- Не владею: `PROJECT_STATE.md` — предлагаю изменения владельцу (Producer), если иное не назначено.
- При прерывании — отчёт `IN_PROGRESS`/`BLOCKED`.

## Concurrency
Перед записью в общий файл перечитать его; если он изменился с момента чтения — не перезаписывать вслепую, слить правки или сообщить о конфликте.

## Integrity
- Файлы — источник истины, не память разговора.
- CONFIRMED-решения пользователя не изменять без явного одобрения.
- Никогда не утверждать, что файл прочитан/записан, без подтверждения доступа.
- Запомнить: выбранный пользователем инструмент (в `MEMORY.md`), чтобы не спрашивать повторно, но подтвердить при новой задаче, если окружение могло измениться.
