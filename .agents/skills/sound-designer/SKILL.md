---
name: sound-designer
description: >-
  Game audio design, sound effects (SFX) production, musical theme direction, and audio mapping skill. Use this skill when creating or planning game audio, generating or sourcing SFX and music, authoring audio prompts, managing audio licenses, or maintaining audio.md audio maps.
---

# Sound-Designer Skill

This skill guides the agent in creating, sourcing, and mapping game audio assets (SFX and background music) according to the project's Concept Document, Game Design Document (GDD), and Art Style Guide.

## Master Agent Specification & Manual
Full instructions, role boundaries, licensing rules, and audio mapping standards:
[Sound-Designer Master Spec](file:///d:/mydocs/GitHub/Agent-Flow/Agents/Sound-Designer/Sound-Designer.md)

---

## Standard Task Sequence

1. **Intake & Discovery (Phases 0–1):**
   - Check personal memory: [MEMORY.md](file:///d:/mydocs/GitHub/Agent-Flow/Agent_Memory/Sound-Designer/MEMORY.md) and task history.
   - Inspect required documents: Concept Document (`docs/concept/CONCEPT_DOCUMENT.md`), GDD (`docs/gdd/`), Art Style Guide (`docs/art/` or `Inputs/Art_Style/`).
   - If any of the 3 documents is missing, set status to `BLOCKED`, notify Producer, and halt execution.
2. **Tool Selection (Phase 2):**
   - Clarify available audio generation/sourcing tools with the user.
   - Set operational mode: `GENERATE`, `SOURCE`, or `PROMPT_ONLY`.
3. **Audio Planning & Approval Gate (Phase 3):**
   - Extract all gameplay actions and scenes from GDD.
   - Formulate sound direction (1–3 sentences defining aesthetic, mood, tempo, instrumentation).
   - Author audio plan in `tasks/` and present to the user.
   - **Do not proceed to mass generation or downloading without explicit user approval.**
4. **Production (Phase 4):**
   - Execute production in approved mode:
     - `GENERATE`: Generate audio files, store in `Assets/Audio/{Sounds,Music}/`, record prompts in `Assets/Audio/Prompts/`.
     - `SOURCE`: Download CC0/CC-BY assets, record source and attribution.
     - `PROMPT_ONLY`: Prepare detailed prompt packages in `Assets/Audio/Prompts/<name>.md`.
5. **Audio Map Indexing (Phase 5):**
   - Populate or update [Assets/Audio/audio.md](file:///d:/mydocs/GitHub/Agent-Flow/Assets/Audio/audio.md).
   - Verify physical presence of all referenced files.
6. **Quality Assurance & Handoff (Phases 6–7):**
   - Validate against [QA_CHECKLIST.md](file:///d:/mydocs/GitHub/Agent-Flow/Agents/Sound-Designer/QA_CHECKLIST.md).
   - Document task report in `Agent_Memory/Sound-Designer/tasks/`.
   - Update `WORK_LOG.md` and send status update to Producer via mailbox or task board.
