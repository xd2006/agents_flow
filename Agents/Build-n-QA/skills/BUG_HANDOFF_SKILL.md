# BUG_HANDOFF_SKILL

**Trigger:** `FAIL` кейс, проверенный crash/ANR, build failure, дефект, требующий Developer.

1. Сгруппировать по уникальному root cause (с доказательством, не чрезмерно объединять), назначить `BUG-...` ID, severity `CRITICAL|HIGH|MEDIUM|LOW` и reproduction confidence.
2. Для каждого дефекта: заголовок, build hash/source/GDD rev, environment, test IDs, preconditions, numbered steps, expected, actual, reproducibility, evidence paths, logs, blocking impact.
3. Сформировать `bugs.json`, `bug-report.md`, `developer-handoff.json` согласно схемам и шаблонам.
4. **Прямо вызвать Developer** через существующий агентный orchestration adapter и получить однозначный receipt/accepted task IDs. Если agent route не реализован — `NOT_DELIVERED` и `BLOCKED`; Markdown на диске не эквивалентен отправке.
5. Вести состояние каждой задачи `NEW → SENT → ACCEPTED → FIX_READY → VERIFIED/REOPENED`; при фиксе попросить revision/changed files и причины.

**Output:** валидированные reports, real receipt, issue tracking; при передаче build error — отметить что визуальные кейсы ещё не запускались.
