# MEMORY_RULES

## Изоляция исходного Unity-проекта
`source_project_root` — **read-only** для Build-n-QA. Поскольку стандартный проектный `Agent_Memory/` внутри исходника противоречил бы запрету записи, использовать отдельный `workspace_root` **вне source**:

```text
<workspace_root>/
  Agent_Memory/
    _Shared/
      PROJECT_STATE.md
      DECISIONS.md
      CONFLICTS.md
      TASK_BOARD.md
      ARTIFACT_INDEX.md
    Build-n-QA/
      MEMORY.md
      WORK_LOG.md
      DECISION_LOG.md
      OPEN_QUESTIONS.md
      tasks/<task_id>/CHECKPOINT.md
  QA_Artifacts/Build-n-QA/<task_id>/<run_id>/
    build-manifest.json
    build.apk
    test-cases.json
    test-results.json
    qa-run-report.md
    bugs.json
    bug-report.md
    developer-handoff.json
    evidence/
    task-report.md
  staging/<task_id>/<run_id>/   # временная копия проекта
```

**Важно:** это layout по умолчанию, не запрет на другие пути: любой mapping допустим только если всё записываемое вне source и доступно соответствующим агентам. Paths в файлах должны быть реальными, не placeholders.

## Правила чтения и записи
- Перед задачей: читать `_Shared/PROJECT_STATE.md`, свою `MEMORY.md`, `TASK_BOARD.md`, релевантные решения и индекс артефактов; не загружать все проекты бесконтрольно.
- Писать durable task record по завершении каждой задачи; `IN_PROGRESS`/`BLOCKED` checkpoints при прерывании.
- Build-n-QA владеет своей папкой и артефактами QA. `_Shared` обновляет лишь в своей зоне; user-confirmed решения в `_Shared/DECISIONS.md` не переписывать.
- При конкурентном редактировании применять lock/версии; если недоступно — сообщать о конфликте, не терять чужие правки.
- Секреты, PII, access tokens в памяти не хранить. Маскировать в логах.
- Скриншоты, APK и логи могут быть большими: сохранять в artifacts, в памяти — ссылки, хеши и краткие итоги.
- Проверять existence/read-after-write перед утверждением о сохранении.
