# OUTPUT_CONTRACT — Sound Designer

## Структура
```text
Assets/Audio/
  Sounds/    <имя_действия>.<ext>
  Music/     <имя_темы_или_сцены>.<ext>
  Prompts/   <имя>.md          (PROMPT_ONLY, а также запись промптов для сгенерированных файлов)
  audio.md                     (индекс; ASSUMPTION A1)
```

## Именование
- SFX: `<имя_действия_в_игре>.<ext>` — идентификатор берётся из GDD; если его нет, агент придумывает его по смыслу (snake_case, CONFIRMED Q3) и помечает `ID: assigned` в `audio.md`.
- Музыка: `<scene_id>.<ext>`; лупы — `<scene_id>_loop.<ext>` (CONFIRMED Q2).
- Один файл на действие, без вариантов (CONFIRMED Q1).
- Промпты: `Prompts/<то же имя>.md`.
- Форматы по умолчанию: SFX — WAV; музыка — OGG (CONFIRMED A4).

## audio.md — обязательная структура
```markdown
# Audio Map
- Project: ...   - Updated: <дата|unknown>   - Mode: GENERATE|SOURCE|PROMPT_ONLY
- Source docs: Concept <версия>, GDD <версия>, Art Style Guide <версия>
- Sound direction: <1–3 предложения из концепта/арт-стайла>

## Sound effects
| Action ID (`assigned` если придуман) | GDD ref | Trigger / description | File | Status | Source | License | Attribution | Prompt |
## Music
| Scene/Theme ID | GDD ref | Mood / tempo / instrumentation | File | Loop | Status | Source | License | Attribution | Prompt |
## Unmapped / gaps
(действия и сцены без звука — с причиной)
## Open questions / conflicts
```
- `Status`: `READY` | `PROMPT_ONLY` | `MISSING` (+причина) | `PLANNED`.
- `File` — относительный путь; пусто, если файла нет.
- `License` — только свободная (CC0, CC-BY и т. п. по A3) либо условия инструмента для сгенерированных; `unknown` недопустимо для `READY`.

## Quality bar / Definition of done
- Каждое действие и каждая сцена из GDD присутствуют в `audio.md`.
- Все `READY`-файлы существуют, имена корректны, лицензия и источник указаны.
- Звук соответствует звуковой эстетике из документов.

## Partial / blocked
Отчёт со статусом `BLOCKED`/`IN_PROGRESS`: что сделано, что нет, что нужно. `audio.md` отражает реальное состояние; не помечать `READY` ничего непроверенного.
