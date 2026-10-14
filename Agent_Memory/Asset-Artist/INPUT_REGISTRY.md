# INPUT_REGISTRY — Asset-Artist

Канонический реестр версий входных документов, по которым создаются и валидируются графические ассеты.
Сверяется перед началом каждой задачи на фазе Discovery.

| input_id | тип | путь | размер | изменён | sha256 | статус | зафиксировано в | ключевые параметры |
|---|---|---|---|---|---|---|---|---|
| *IN-INIT* | System | *None* | — | 2026-10-14 | — | ACTIVE | INIT | Первичная инициализация реестра |

### Типы входов:
- `Art_Style`: Арт-стайл гайд (владелец: `Art-Style-Guide-Agent`, путь: `Inputs/Art_Style/` или `docs/art/`)
- `GDD`: Документ геймдизайна (владелец: `Game-Designer-Agent`, путь: `Inputs/GDD/` или `docs/gdd/`)
- `Format_Specs`: Спецификация форматов графики (владельцы: `Art-Style-Guide-Agent`, `Developer-Agent`, путь: `Inputs/Format_Specs/`)
- `References`: Пакет визуальных референсов (владелец: `Art-Style-Guide-Agent`, путь: `Inputs/References/` или `docs/art/references/`)
- `Developer_Answer`: Технические параметры движка и интеграции (владелец: `Developer-Agent`)

### История изменений входов:
| дата | input_id | что изменилось | затронутые ассеты → NEEDS_REVIEW |
|---|---|---|---|
| 2026-10-14 | — | Инициализация реестра | — |
