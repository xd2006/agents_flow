---
name: art-style-guide
description: >-
  Game visual direction, art style guide, and reference documentation skill. Use this skill when
  the user asks to create, review, update, or structure art style guides, visual style bibles,
  aesthetic pillars, color palettes, silhouette rules, and organized local art references.
---

# Art-Style-Guide-Agent Skill

This skill guides the agent in authoring comprehensive, self-contained game art style guides and managing verified local art references according to the project's visual direction.

## Master Agent Specification & Manual
Full instructions, role boundaries, and output contracts:
[Art-Style-Guide-Agent Master Spec](file:///d:/mydocs/GitHub/Agent-Flow/Agents/Art-Style-Guide-Agent/Art-Style-Guide-Agent.md)

---

## Standard Task Sequence

1. **Context & Discovery:**
   - Inspect [MEMORY.md](file:///d:/mydocs/GitHub/Agent-Flow/Agent_Memory/Art-Style-Guide-Agent/MEMORY.md), [PROJECT_STATE.md](file:///d:/mydocs/GitHub/Agent-Flow/Agent_Memory/_Shared/PROJECT_STATE.md), and concept documents.
   - Identify target guide directory (defaults to `docs/art/`) and existing art documentation.
2. **Completeness & Reference Verification:**
   - Extract visual requirements and existing references.
   - **Hard Rule:** References must originate solely from the concept document or user. Never search the web or generate AI images to replace references.
   - If references are insufficient or missing, ask the user and pause or proceed text-only with explicit approval.
3. **Guide Authoring:**
   - Write a self-contained art style guide: aesthetic pillars, emotional tone, forms, silhouettes, color palette, lighting, textures, characters, environment, UI/VFX, and strict "Do's and Don'ts".
   - The guide must be completely understandable and actionable without looking at reference images.
4. **Artifact Placement:**
   - Save the guide as `docs/art/ART_STYLE_GUIDE.md` (or project-specified path).
   - Place permitted references into a local `references/` subfolder alongside the guide with relative links.
5. **QA & Reporting:**
   - Verify against [QA_CHECKLIST.md](file:///d:/mydocs/GitHub/Agent-Flow/Agents/Art-Style-Guide-Agent/QA_CHECKLIST.md).
   - Record execution in `Agent_Memory/Art-Style-Guide-Agent/tasks/`.
   - Update `WORK_LOG.md`, `DECISION_LOG.md`, and shared project records.
