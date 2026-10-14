# SKILLS — реестр навыков Asset Artist

Все пути указаны относительно `Agents/asset-artist/`.

| Навык | Тип | Когда вызывать | Вход | Выход |
|---|---|---|---|---|
| `DISCOVERY_SKILL.md` | обязательный | в начале каждой задачи и при повторном входе | задача, память, входы | Asset Brief, классы блокировок |
| `DOCUMENTATION_SKILL.md` | обязательный | в конце задачи, при прерывании или блокировке | итоги работы | отчёт в `tasks/`, строка в `WORK_LOG.md` |
| `DECISION_LOG_SKILL.md` | обязательный | при существенном решении или утверждении | решение и контекст | запись `DEC-AA-###` |
| `skills/INPUT_INTAKE_SKILL.md` | доменный | внутри Discovery | `Inputs/*` | `INPUT_REGISTRY.md`, список пробелов и конфликтов |
| `skills/INPUT_REQUEST_SKILL.md` | доменный | когда есть пробел, конфликт, изменение входа или неизвестны требования движка | пробелы | `_Shared/REQUESTS/REQ-AA-####.md` |
| `skills/ASSET_PRODUCTION_SKILL.md` | доменный | на фазах 3–5 | Asset Brief, возможности | план, style test, ассеты, пакеты промптов |
| `skills/ASSET_VALIDATION_SKILL.md` | доменный | на фазах 6–7 | ассеты-кандидаты | QA-результаты, выдача, манифест |

Зависимости между навыками:
- Discovery вызывает Intake.
- Intake передаёт найденное в Request.
- Production использует утверждённый style profile.
- Validation опирается на канонический `QA_CHECKLIST.md`.
- Все навыки пишут память по `MEMORY_RULES.md`.

Шаблоны: `templates/INPUT_REQUEST.md`, `templates/TASK_REPORT.md`, `templates/ASSET_MANIFEST.md`, `templates/INPUT_REGISTRY.md`, `templates/STYLE_TEST.md`.
