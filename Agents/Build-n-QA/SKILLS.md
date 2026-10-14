# SKILLS — реестр

## Обязательные, всегда доступные
| Skill | Когда | Канонический файл |
|---|---|---|
| Discovery | Перед выполнением, при новом блокере | `DISCOVERY_SKILL.md` |
| Documentation | Завершение, блокировка, результат каждой задачи | `DOCUMENTATION_SKILL.md` |
| Decision Log | Любое существенное решение / конфликт | `DECISION_LOG_SKILL.md` |

## Доменные
| Skill | Триггер | Файл | Основной результат |
|---|---|---|---|
| Asset Handoff | Фаза 1, перед staging/build | `skills/ASSET_HANDOFF_SKILL.md` | staging asset manifest |
| Unity Build | Фаза 1 и каждый повторный билд | `skills/UNITY_BUILD_SKILL.md` | APK + build manifest |
| GDD Tests | Фаза 2, изменение GDD | `skills/GDD_TEST_SKILL.md` | test-cases JSON |
| Emulator Control | Фаза 3 / retest | `skills/EMULATOR_CONTROL_SKILL.md` | device info + screenshot/control |
| Visual QA | Фаза 3 / retest | `skills/VISUAL_QA_SKILL.md` | evidence + test results |
| Bug Handoff | FAIL или ошибка build | `skills/BUG_HANDOFF_SKILL.md` | report + Developer receipt |
| Regression | Получена новая ревизия от Developer | `skills/REGRESSION_SKILL.md` | retest + regressions |

Прямой вызов другого агента, файловая запись, Unity, ADB и vision — **внешние capabilities** с обязательным контрактом `adapters/RUNTIME_CONTRACT.md`.
