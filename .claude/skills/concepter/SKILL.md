---
name: concepter
description: >-
  Game concept design and pre-GDD specification skill. Use this skill when the user asks to create,
  refine, critique, or structure initial game concepts for Mobile or Steam/PC, evaluate gameplay loops,
  and generate structured GDD handoff documents.
---

# Concepter-Agent Skill

This skill guides the agent in creating critically analyzed, compact game concept documents (2–3 pages) for Mobile or Steam/PC and preparing deterministic, machine-readable `GDD_HANDOFF` blocks for downstream GDD specialists.

## Master Agent Specification & Manual
Full instructions, invariant rules, and the 14 mandatory sections:
[Concepter-Agent Master Spec](file:///d:/mydocs/GitHub/Agent-Flow/Agents/Concepter-Agent/Concepter-Agent.md)

---

## Standard Task Sequence

1. **Discovery & Input Analysis:**
   - Inspect user prompts, target platform (Mobile or Steam/PC), audience, and core fantasy.
   - Separate `USER REQUIREMENT` from `PROPOSAL` and `ASSUMPTION`.
2. **Clarification & Critique:**
   - Ask focused follow-up questions for critical unknowns (avoid giant questionnaires).
   - Provide constructive criticism with causes, risks, and alternatives. Do not automatically flatter the idea.
   - Do not perform web research unless explicitly requested by the user.
3. **Draft Concept Document:**
   - Write a concise Markdown document (~2–3 pages) covering all 14 mandatory sections in exact order.
   - Append `Assumptions, Decisions, Constraints & Open Questions` and the machine-readable YAML `GDD_HANDOFF` block.
   - Mark status explicitly as `DRAFT`.
4. **User Approval Gate:**
   - Present the draft and ask explicitly: *"Do you approve this concept document revision?"*
5. **Finalization & Handoff:**
   - Upon explicit approval, update status to `APPROVED`.
   - Save the document (e.g. `docs/concept/CONCEPT_DOCUMENT.md`) and log task outcome in `Agent_Memory/Concepter-Agent/tasks/`.
   - Update `WORK_LOG.md` and shared project state.
