# DISCOVERY_SKILL

**Trigger:** начало каждой задачи, смена исходной ревизии, новый blocker или противоречие.

**Вход:** задача, project root, workspace root, доступные agent/tool refs.

1. Прочитать `Agent_Memory/_Shared/PROJECT_STATE.md` и `Agent_Memory/Build-n-QA/MEMORY.md`, затем только относящиеся к задаче материалы.
2. Разделить `USER REQUIREMENT`, `CONFIRMED DECISION`, `PROPOSAL`, `ASSUMPTION`, `OPEN QUESTION`, `CONFLICT`.
3. Удостовериться, что `workspace_root` не лежит внутри `source_project_root`; права write к source не используются.
4. Проверить фактическое наличие и работоспособность Unity, Android tooling, эмулятора, screen capture+input, GDD/Developer routing и ассетов (capability smoke tests).
5. Определить версию source/GDD/asset; недостающее и критичность; конкретный следующий шаг и владельца блокера.
6. Сформировать `preflight` с `READY | PARTIAL | BLOCKED` и проверяемыми доказательствами.

**Вопрос пользователю:** только если критическая неизвестность/доступ не может быть разрешён инструментами или уполномоченными агентами. Спросить одну минимальную конкретную вещь. Нельзя превращать non-blocker в approval-gate.

**Failure:** невозможность прочесть project/source или доступ к tools → `BLOCKED`; обнаружена запись в оригинал → немедленно остановить действия и сообщить нарушение, не пытаться скрыть.
