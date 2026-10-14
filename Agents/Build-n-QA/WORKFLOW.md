# WORKFLOW — стадии, переходы и recovery

## Состояния
`NEW → DISCOVERING → BUILDING → PLANNING → TESTING → REPORTING → WAITING_DEVELOPER → RETESTING → DONE`

Ответвления: `BUILD_FAILED → REPORTING`; любая фаза → `BLOCKED` / `FAILED`; `RETESTING` → `BUILDING` / `TESTING` по получении новой ревизии. `BLOCKED` означает необходим внешний ввод/инструмент; `FAILED` — подтверждённый технический отказ задачи; `STALLED` — повторяющийся безрезультатный `BLOCKED`.

**Нет approval-gates между фазами.** Есть только проверки готовности и реальные blockers.

## 0. Discovery
Вход: запрос, reference проекта.  
Действия: прочитать память и актуальную конфигурацию; проверить права чтения source и записи вне source, версию Unity, Android Build Support, лицензию, CLI, SDK/ADB, список установленных эмуляторов, screen/vision/action-capabilities; проверить GDD и Developer adapters и asset source.  
Выход: preflight report, изолированный workspace, список рисков, snapshot ID.  
Если чего-то не хватает, но можно продолжить другие безопасные проверки — продолжить; блокирующее отсутствие отмечать точно.

## 1. Сборка и ассеты
1. Снять fingerprint исходника до действий (git HEAD + dirty status + дополнительно хешируемые критичные файлы, если доступны).
2. Создать **полную рабочую копию** вне original source; исключать только безопасно воспроизводимые кэши. Не использовать изменяемые symlinks/junctions на source.
3. Получить утверждённые asset revisions с provenance и checksum, разместить **в staging**; конфликты с существующими ассетами без правил замены — blocker.
4. Определить имеющийся build entrypoint или создать временный Editor build-driver **только в staging**.
5. Собрать Unity `Development` APK; не AAB; проверить расширение, installability (если возможно), build log, fingerprint и exit code.
6. Повторно сверить инвариант исходника; сохранить APK и `build-manifest.json`.

**Неуспех:** ошибки компиляции / несовместимость ассетов → `BUILD_FAILED`, доказательства → Developer; агент не редактирует оригинал. Если отсутствует требуемый build tool / license — `BLOCKED`.

## 2. GDD / тест-кейсы
1. Обратиться к GDD-агенту через реальный adapter, запросить готовые тест-кейсы с ID, priority, preconditions, actions, expected, requirement links и GDD revision.
2. Если кейсов нет, запросить доступ к **каноническому GDD**, вывести измеримые тесты, отметить `derived_from_gdd`; попросить GDD-агента разрешить неоднозначности, не придумывать ожидаемый результат.
3. Нормализовать JSON, проверить схему, unique IDs, обязательные кейсы, покрытие scope и версию GDD.
4. `BLOCKED`, если нет ни кейсов, ни исходного GDD, или тест не имеет определимого expected outcome.

## 3. Автономный запуск и QA
1. Перечислить установленные эмуляторы, выбрать совместимый (Android API/ABI/ориентация/разрешение) по проверяемым признакам. Новый не устанавливать.
2. Запустить/подключить выбранный, проверить ADB; установить **конкретный** APK по build hash; сохранить metadata устройства.
3. Для каждого кейса восстановить precondition, исполнить реальные действия (tap/swipe/back/text); делать скриншоты, logs/trace и проверять postconditions; при ошибке записать повторяемый сценарий.
4. `PASS` только после наблюдения actual == expected; `FAIL` при достоверном расхождении; `BLOCKED` при недоступном окружении/данных; `NOT_RUN` если не исполнялся. Не маскировать flaky тесты.
5. Сохранить `qa-run-report.md`, машиночитаемые результаты, evidence mapping.

## 4. Handoff
1. Дедуплицировать баги, определить severity по влиянию, добавить build/GDD/version, steps, expected/actual, evidence, frequency.
2. Создать `bug-report.md` и `bugs.json`, сериализовать запрос по `contracts/agent_handoff.schema.json`.
3. Через реальный orchestrator **вызвать** Developer, получить receipt / task IDs и сохранить их. Нет ack — статус передачи `NOT_DELIVERED`.
4. Изменения GDD и требования → отдельный запрос к GDD-агенту; не выдавать это за баг кода.

## 5. Исправления, повторное QA
1. Ждать event/poll от Developer через фактически поддерживаемый механизм, без фиктивной фоновой работы; получить commit/revision/change summary и устранённые IDs.
2. Новый snapshot Developer-версии → новая staging-копия → новый APK; никогда не редактировать source напрямую.
3. Выполнить ретест всех затронутых кейсов плюс зависимую регрессию и остальные ещё не прошедшие обязательные кейсы. `PASS` предыдущего билда не переносить автоматически на новый APK без обоснованной повторной проверки.
4. Отправлять новые/оставшиеся дефекты; цикл без установленного предела итераций, **но** при отсутствии новой Developer revision и новых применимых данных — `STALLED/BLOCKED` с описанием необходимого внешнего результата.
5. `DONE` только когда **все обязательные кейсы** актуальной версии имеют `PASS` на одном актуальном билде, evidence есть, оригинал Build-n-QA не менял и отчёт сохранён.

## Восстановление
На каждой границе фазы записывать checkpoint вне исходного проекта: task/run IDs, phase, artifact hashes, last successful action, очередной шаг, blockers. После restart перепроверять актуальность файлов, APK и GDD; не доверять stale PASS от другого build ID. При конкурентной записи общей памяти использовать optimistic concurrency/lock, иначе report conflict.
