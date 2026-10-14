# QA_CHECKLIST агента

## Preflight
- [ ] `source_project_root` найден и доступен только на чтение со стороны Build-n-QA.
- [ ] `workspace_root` реально вне source, нет mutable symlinks в source.
- [ ] Установлена подходящая Unity + Android Build Support, SDK/ADB, рабочая лицензия.
- [ ] Найден доступный **установленный** эмулятор, screen capture, контролируемый input и vision.
- [ ] GDD-agent или GDD реально доступны; Developer handoff способен дать receipt.
- [ ] Assets доступные/проверенные, provenance и checksum записаны.

## Build
- [ ] Изоляция и snapshot до / после.
- [ ] Unity собирает **Development APK**, не AAB, exit success + actual file + sha256.
- [ ] build logs, unity version, source/asset revisions зафиксированы.
- [ ] Оригинал не был изменён Build-n-QA.

## Test planning & QA
- [ ] Кейсы привязаны к каноническому GDD, без придуманных expected.
- [ ] Каждый required кейс имеет actions/preconditions/observable expected.
- [ ] Запущен конкретный APK на зафиксированном emulator ID.
- [ ] У каждого выполненного кейса evidence; FAIL имеет repro и observed actual.
- [ ] Неконтролируемые/непроверенные кейсы `BLOCKED`/`NOT_RUN`, не `PASS`.

## Handoff & retest
- [ ] Баги привязаны к test/build/GDD, severity и evidence.
- [ ] Developer действительно вызван, receipt сохранён.
- [ ] Новый Developer revision идентифицирован, новый APK построен.
- [ ] Re-test и зависимая регрессия выполнены на том же новом build ID.
- [ ] При отсутствии прогресса — остановка `STALLED/BLOCKED`, а не фиктивная вечная работа.

## Final
- [ ] Все **required** кейсы PASS на текущей сборке.
- [ ] Memory, log, decision record и task report сохранены с read-after-write.
- [ ] Все ссылки/пути существуют, схемы прошли валидацию.
- [ ] Незакрытых блокеров, скрытых ошибок, ложных «сделано» нет.
