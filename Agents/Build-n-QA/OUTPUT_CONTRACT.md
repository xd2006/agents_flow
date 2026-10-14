# OUTPUT_CONTRACT

## Статусы
**Task:** `NEW | IN_PROGRESS | WAITING_DEVELOPER | DONE | BLOCKED | FAILED`; `STALLED` записывать как subtype `BLOCKED`.  
**Test:** `PASS | FAIL | BLOCKED | NOT_RUN`.  
**Handoff:** `PREPARED | DELIVERED | ACKNOWLEDGED | NOT_DELIVERED`.

## Обязательные артефакты
| Файл | Когда | Требования |
|---|---|---|
| `build-manifest.json` | после сборки | schema, hash исходников и APK, version, unity/target, BuildOptions, build log path |
| `build.apk` | успешная сборка | Android Development APK, installable (если эмулятор доступен) |
| `test-cases.json` | перед QA | schema, ID, source GDD revision, steps и expected |
| `test-results.json` | после QA | build ID, test ID, status, evidence refs, observed actual |
| `qa-run-report.md` | после QA | summary и таблица PASS/FAIL/BLOCKED/NOT_RUN |
| `bugs.json` + `bug-report.md` | при FAIL / build errors | reproducibility, severity, evidence, current build |
| `developer-handoff.json` | при передаче | requested action, issue IDs, status/receipt |
| `task-report.md` | на завершении/blocked | checklist `DOCUMENTATION_SKILL.md` |

`contracts/` определяет минимальный интерфейс для `build-manifest.json`, `test-cases.json`, `bugs.json` и `developer-handoff.json`. Для `test-results.json` использовать `contracts/test-results.schema.json`.

## Ключи прослеживаемости
`task_id`, `run_id`, `source_revision`, `gdd_revision`, `build_id`, `apk_sha256`, `test_id`, `requirement_id`, `bug_id`, `developer_handoff_id`, `developer_revision`. Никогда не смешивать факты двух сборок в один `PASS`.

## Качество результата
- `PASS` требует реального наблюдения, postcondition и evidence; не допускается оценка по намерению.
- В репорте фиксировать окружение, Android API, эмулятор/ABI, шаги, расхождения и повторяемость.
- Баги с доказательствами должны быть доступны Developer по реальному пути/URI.
- Отсутствие ack от Developer → `NOT_DELIVERED`, даже если Markdown уже записан.
- `DONE` только после `PASS == total_required` и `FAIL == BLOCKED == NOT_RUN == 0` для обязательных кейсов на актуальной сборке.
- Внеобязательные кейсы могут оставаться вне scope, но должны быть явно отделены.

## Имена
`<task_id>/<run_id>/` — версионированные каталоги запусков. Не перезаписывать evidence предшествующей сборки. Хешировать перед публикацией. Результаты `BLOCKED/FAILED` также сохранять, когда runtime позволяет.
