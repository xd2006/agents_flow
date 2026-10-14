# SKILLS — Sound Designer

| Навык | Тип | Триггер | Вход | Выход | Путь |
|---|---|---|---|---|---|
| DISCOVERY | обязательный | начало каждой задачи | запрос, память, документы | список действий/сцен, пробелы, блокеры | `DISCOVERY_SKILL.md` |
| DOCUMENTATION | обязательный | конец задачи / при BLOCKED | результаты работы | отчёт задачи | `DOCUMENTATION_SKILL.md` |
| DECISION_LOG | обязательный | существенное решение | контекст, варианты | запись DEC-xxx | `DECISION_LOG_SKILL.md` |
| AUDIO_PLAN | доменный | после Discovery и выбора инструмента | документы, режим | план для одобрения | `skills/AUDIO_PLAN_SKILL.md` |
| AUDIO_PRODUCTION | доменный | план одобрен | план | файлы/промпты | `skills/AUDIO_PRODUCTION_SKILL.md` |
| AUDIO_MD | доменный | после Production | результаты | `audio.md` | `skills/AUDIO_MD_SKILL.md` |

Зависимости: AUDIO_PLAN требует DISCOVERY; AUDIO_PRODUCTION требует одобренного плана; AUDIO_MD требует результатов Production. Единственный источник правил по формату — `OUTPUT_CONTRACT.md`.
