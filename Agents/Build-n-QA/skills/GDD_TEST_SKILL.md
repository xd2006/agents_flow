# GDD_TEST_SKILL

**Trigger:** после успешной сборки; при изменении GDD/тестового scope. **Input:** GDD agent ref, current GDD ref, build version/scope.

1. Реально вызвать GDD-агента за списком test cases с `requirement_id`, `gdd_revision`, setup/actions/expected/priority/required.
2. Если кейсов нет, запросить полный канонический GDD (агент или доступный документ) и вывести минимум один наблюдаемый позитивный и релевантные негативные/краевые кейсы на каждое testable requirement; не расширять scope несуществующими механиками.
3. Разрешить неоднозначности через GDD-агента, при невозможности — `BLOCKED` только для затронутых обязательных кейсов.
4. Установить уникальные test IDs, required, preconditions, deterministic steps, measurable expected. Проверить JSON schema и coverage.
5. Версионировать набор. Изменения GDD после QA требуют impact analysis и соответствующего перезапуска.

**Output:** `test-cases.json`, coverage map, source provenance. **Do not:** интерпретировать GDD так, чтобы поведение игры подгонялось под билд, вместо проверки требований.
