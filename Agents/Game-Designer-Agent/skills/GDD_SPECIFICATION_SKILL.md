---
name: gdd-specification
description: Use when drafting, reviewing, or updating a game design document or feature specification from approved requirements.
---

# GDD Specification Skill

## Purpose
Create a specification that tells each relevant discipline what to implement and how to validate it. It is not a story or a speculative design brainstorm unless the user explicitly asks for ideation.

## Prerequisites
- Run `DISCOVERY_SKILL.md` first.
- Read canonical requirements and approved references.
- Identify the intended format and whether the user authorized generation or only wants analysis/briefing.

## Procedure
1. Confirm the feature title, purpose, scope, affected systems, entry points and player-facing outcome.
2. Capture goals and target metrics only when supplied or explicitly approved; never invent business targets.
3. Define acceptance criteria by relevant role (Player, Product, Design, Client/Engineering, Backend when relevant, Art, UI/UX, Analytics, QA, etc.).
4. Define terminology and shared vocabulary.
5. Describe the operation and user effect in a concise overview.
6. Specify player story, journey stages, actions, states, transitions, and entry/exit conditions.
7. Define functional flows with explicit branches and errors. If diagrams cannot be generated, provide readable Mermaid or structured text when appropriate.
8. Describe meaningful use cases with preconditions, trigger, main flow, alternative/error flows, result and dependencies.
9. Specify significant processes: purpose, trigger, preconditions, inputs, validation, processing, state changes, outputs, errors, dependencies and analytics.
10. Cover edge cases: invalid input, duplicates, reconnect/restart, missing data, failure, interruption, expiry, limits, desync and rollback where relevant.
11. Specify Art and UI/UX requirements: elements, purpose, states, visibility, interaction, feedback, loading/error/empty states, localization, animation/VFX triggers and references as applicable.
12. Specify economy/configs, narrative, sound and analytics only when relevant. Do not invent material values. Analytics events must name parameters, types, allowed values/catalogues and purpose where known.
13. Write test cases linked to acceptance criteria and edge cases.
14. Mark every unresolved choice as a proposal, assumption, open question or conflict.
15. Run `QA_CHECKLIST.md` and complete the handoff.

## Reference principles adapted from GDD Sam
- Collect requirements, detect gaps/conflicts, ask questions, and get approval before final generation when material uncertainties remain.
- Distinguish user requirements, confirmed decisions, proposals, assumptions, open questions and conflicts.
- Do not silently make significant decisions.
- Prefer complete coverage with concise text and minimal duplication.
- The document answers “WHAT MUST THE TEAM DO?”
- Include objective acceptance criteria and tests.
- Do not turn the GDD into a full architecture/API/database/infrastructure specification.

## Output
Return the requested artifact plus a short validation summary, remaining questions/blockers, and handoff notes. Do not claim diagrams, images, DOCX, or tests were generated unless the runtime confirms it.
