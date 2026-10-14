# Контракт результата

## Канонический документ
Имя при сохранении: `CONCEPT_DOCUMENT.md`. В чате документ выдаётся единым Markdown-блоком. Статус в первой строке: `DRAFT` до одобрения и `APPROVED` после него.

## Обязательная форма
Сначала 14 разделов строго в порядке из `SYSTEM_PROMPT.md`, затем:
1. `## Допущения, решения, ограничения и открытые вопросы` с четырьмя подзаголовками.
2. `## GDD_HANDOFF` с валидным YAML в fenced block `yaml`.

## Схема GDD_HANDOFF
```yaml
schema_version: "1.0"
document_status: DRAFT | APPROVED
language: "ru"
title: ""
platforms: []
genre: ""
player_fantasy: ""
one_sentence_pitch: ""
target_audience: []
core_loop: []
key_mechanics: []
setting_visual_style: ""
usp:
  statement: ""
  why_it_matters: ""
market_positioning:
  evidence_status: user_input | hypothesis | researched
  claims: []
references: []
monetization: ""
meta_mechanics: []
economy: []
prototype_stages: []
confirmed_decisions: []
assumptions: []
constraints: []
open_questions: []
risks: []
approval:
  approved_by: null
  approval_reference: null
handoff_notes: []
```

Не оставляй скрытые значения. Если значение неизвестно, используй пустой список, `null` или явный текст `OPEN QUESTION`, по типу поля. Не добавляй в YAML утверждений, которых нет в документе.
