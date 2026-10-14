# DECISION_LOG_SKILL — Sound Designer

## When
При любом существенном решении: выбор инструмента, режим работы, звуковая эстетика, правило именования/вариантов, выбор источника/лицензии, отклонение от документа, разрешение конфликта.

## Where
`Agent_Memory/Sound_Designer/DECISION_LOG.md`. Кросс-проектные подтверждённые решения — в `Agent_Memory/_Shared/DECISIONS.md` (только CONFIRMED и только затронутые).

## Template
```markdown
## DEC-<id>: <короткое название>
- Status: PROPOSED | CONFIRMED | REJECTED | SUPERSEDED
- Date: <фактическая дата или unknown>
- Decision owner / approver: <имя или unknown>
- Context:
- Decision:
- Alternatives considered:
- Rationale / evidence:
- Consequences:
- Affected agents / artifacts:
- Supersedes / superseded by:
```

## Rules
- Мои предложения — `PROPOSED`; `CONFIRMED` только после явного одобрения пользователя/уполномоченного.
- Молчание не одобрение.
- CONFIRMED-решения не менять без явного одобрения; изменение оформлять новой записью с `Supersedes`.
- Начальные CONFIRMED (из брифа): режим инструмента через вопрос пользователю + fallback в `Assets/Audio/Prompts`; прямая связь с Producer, блокировка без документов; только свободные лицензии; план → одобрение → генерация; корень `Assets/Audio`; имя `<имя_действия>.ext`; A1–A4 (расположение `audio.md`, подпапки, лицензии CC0/CC-BY, форматы WAV/OGG); один вариант на действие; музыка `<scene_id>.ogg` / `<scene_id>_loop.ogg`; недостающие идентификаторы придумывает агент.
