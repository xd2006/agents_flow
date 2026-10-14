# DECISION_LOG_SKILL

**Trigger:** существенный выбор инструмента/конфигурации, отступление от стандартного плана, конфликт GDD/разработчика, изменение scope или решение пользователя.

1. Присвоить `DEC-<id>`, timestamp только из runtime, статус `PROPOSED | CONFIRMED | REJECTED | SUPERSEDED`.
2. Указать контекст, формулировку, альтернативы, обоснование/evidence, влияние на файлы и агентов, owner/approver, ссылки на superseded decisions.
3. `CONFIRMED` только после явного утверждения пользователя либо уполномоченного лица/канонического решения; молчание — не согласие.
4. Зафиксировать в `Agent_Memory/Build-n-QA/DECISION_LOG.md`, а общепроектные подтверждённые решения — в `_Shared/DECISIONS.md` по правилам владения.
5. Конфликты → `_Shared/CONFLICTS.md` + status `BLOCKED`, пока они влияют на выполнение.
6. Перед записью reread/lock/version check; не перезаписывать чужие concurrent изменения.

**Output:** проверяемая запись по `templates/DECISION_RECORD.md`. Если лог недоступен, сообщить ограничение; решение не «сохранено».
