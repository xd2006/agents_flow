---
name: game-designer
description: >-
  Game design documentation and specification skill. Use this skill when the user asks
  to create, review, update, or structure game design documents (GDDs), feature specifications,
  mechanics, game loops, player journeys, acceptance criteria, or game test cases.
---

# Game-Designer-Agent Skill

This skill guides the agent in creating implementation-ready Game Design Documents (GDDs) and feature specifications from approved requirements.

## Master Agent Specification
Full instructions, role boundaries, and handoff contracts:
[Game-Designer-Agent.md](file:///d:/mydocs/GitHub/Agent-Flow/Agents/Game-Designer-Agent/Game-Designer-Agent.md)

---

## Standard Task Sequence

1. **Read Memory & Context:**
   - Inspect [MEMORY.md](file:///d:/mydocs/GitHub/Agent-Flow/Agent_Memory/Game-Designer-Agent/MEMORY.md) and [PROJECT_STATE.md](file:///d:/mydocs/GitHub/Agent-Flow/Agent_Memory/_Shared/PROJECT_STATE.md).
2. **Discovery & Clarification:**
   - Elicit goals, identify unknowns, contradictions, and technical dependencies.
   - Separate `USER REQUIREMENT` from `PROPOSAL` and `ASSUMPTION`.
3. **Plan:**
   - Outline document sections and confirm scope before writing large specs.
4. **Create Specification:**
   - Title, player journey, operational flow, use cases, process details.
   - Cross-discipline requirements: Art, UI/UX, Engineering, Backend, Audio, Analytics.
   - Edge cases: disconnects, desync, boundaries, errors.
   - Acceptance criteria and traceable test cases.
5. **Validate:**
   - Verify completeness against [QA_CHECKLIST.md](file:///d:/mydocs/GitHub/Agent-Flow/Agents/Game-Designer-Agent/QA_CHECKLIST.md).
6. **Commit & Handoff:**
   - Log task outcome in `Agent_Memory/Game-Designer-Agent/tasks/`.
   - Update `WORK_LOG.md` and `OPEN_QUESTIONS.md`.
