# REGRESSION_SKILL

**Trigger:** Developer вернул реальную новую source revision и список исправлений.

1. Проверить реальный Developer receipt, change set/commit, версии GDD/assets; не использовать непроверенный текст «исправлено» как факт.
2. Сделать новый isolated staging из новой source revision, затем новый APK с новым build_id/hash.
3. Выполнить targeted retests багов, связанные кейсы (dependency graph), smoke/core flows и **все remaining required tests**, чтобы получить 100% PASS на одном актуальном билде.
4. Переоткрыть баг при повторном FAIL с evidence и source revision; новые regression bugs передать через Bug Handoff.
5. Не смешивать результаты разных APK. Запись «предыдущий PASS» — историческая, не критерий для нового release candidate без новой проверки.
6. Если Developer не возвращает новую ревизию или иной проверяемый результат, необходимый для следующего QA, сообщить `STALLED/BLOCKED`; продуктивные итерации не имеют заранее заданного лимита.

**Output:** новый run, regression matrix, bug statuses, финальный verdict. **DONE:** required=all PASS, no BLOCKED/NOT_RUN/FAIL, запись результатов сохранена.
