---
name: prototype-producer
description: >-
  Game prototype producer, planning, and multi-agent development coordinator skill. Use this skill
  when translating game concepts into verifiable requirements, coordinating system GDDs with Game Designer,
  reviewing GDD coverage, authoring development plans, or tracking multi-agent execution.
---

# Prototype-Producer Skill

This skill guides the agent in coordinating game prototype preparation: analyzing concepts and environment constraints, tasking Game-Designer-Agent with modular GDDs, auditing GDD coverage, authoring development plans, and orchestrating execution across peer agents upon explicit user launch commands.

## Master Agent Specification & Manual
Full instructions, role boundaries, and traceability contracts:
[Prototype-Producer Master Spec](file:///d:/mydocs/GitHub/Agent-Flow/Agents/Prototype-Producer/Prototype-Producer.md)

---

## Standard Task Sequence

1. **Discovery & Requirements Breakdown:**
   - Inspect [MEMORY.md](file:///d:/mydocs/GitHub/Agent-Flow/Agent_Memory/Prototype-Producer/MEMORY.md), [PROJECT_STATE.md](file:///d:/mydocs/GitHub/Agent-Flow/Agent_Memory/_Shared/PROJECT_STATE.md), game concept (`docs/concept/CONCEPT_DOCUMENT.md`), and technical setup (`docs/setup/TECHNICAL_SPEC.md`).
   - Extract requirements into `docs/producer/REQUIREMENTS.md` with unique `REQ-ID` tags and build the traceability matrix (`docs/producer/TRACEABILITY.md`).
2. **Game Designer Tasking & GDD Audit:**
   - Formulate system GDD assignments for Game-Designer-Agent via mailbox (`Agent_Memory/_Mailbox/GameDesigner/` or shared memory).
   - Audit received GDDs against requirements: return gaps/defects to Game Designer; package constructive enhancements into `docs/producer/RECOMMENDATIONS.md`.
3. **Development Planning:**
   - Author `docs/producer/DEVELOPMENT_PLAN.md` with ordered tasks (`TASK-###`), dependencies, assigned roles/agents, priorities, and verification criteria.
   - Present plan to the user for explicit approval.
4. **Execution & Task Tracking:**
   - Await explicit user launch command.
   - Issue tasks to peer agents (Architect, Developer, Artist, Sound Designer).
   - Track progress and verify task reports in project files.
5. **Memory Synchronization & QA:**
   - Record execution in `Agent_Memory/Prototype-Producer/tasks/`.
   - Update `WORK_LOG.md`, `DECISION_LOG.md`, and shared project state.
