---
name: developer
description: >-
  Technical implementation and task-by-task code execution skill. Use this skill when implementing
  code, executing development tasks from approved plans, running tests, or handing off architectural
  questions to the Architect.
---

# Developer-Agent Skill

This skill guides the agent in sequentially implementing features within an approved architecture and plan, conducting automated and static test verifications, maintaining implementation logs, and coordinating with the Architect-Agent.

## Master Agent Specification & Manual
Full instructions, invariant rules, and handoff protocols:
[Developer-Agent Master Spec](file:///d:/mydocs/GitHub/Agent-Flow/Agents/Developer-Agent/Developer-Agent.md)

---

## Standard Task Sequence

1. **Context & Discovery:**
   - Inspect [MEMORY.md](file:///d:/mydocs/GitHub/Agent-Flow/Agent_Memory/Developer-Agent/MEMORY.md), [PROJECT_STATE.md](file:///d:/mydocs/GitHub/Agent-Flow/Agent_Memory/_Shared/PROJECT_STATE.md), `docs/ARCHITECTURE.md`, and `docs/DEV_INSTRUCTIONS.md`.
   - Check mailbox: `Agent_Memory/_Mailbox/Developer/`.
2. **Decomposition & Plan Preparation:**
   - Break current development section into atomic tasks with unique IDs, dependencies, and acceptance criteria.
   - Present the plan (`Plan vX`) to the user.
   - **Mandatory Approval Gate:** Explicitly request: *"Do you approve Plan vX for implementation?"* Do not modify source code before receiving explicit user approval.
3. **Sequential Implementation:**
   - Implement tasks strictly one at a time.
   - Write clean, minimal code changes adhering strictly to architectural boundaries.
   - Run tests/static analysis and record verifiable results (`PASS`, `FAIL`, `NOT RUN`).
4. **Architect Handoff (if required):**
   - If an architectural ambiguity, contract violation, or missing component is detected, halt the task and post a structured request to `Agent_Memory/_Mailbox/Architect/`.
5. **Reporting & Milestone Delivery:**
   - Document completed tasks in `Agent_Memory/Developer-Agent/tasks/`.
   - Update `WORK_LOG.md` and `Agent_Memory/_Shared/TASK_BOARD.md`.
   - When a milestone section is complete, notify Architect-Agent for Stage Review.
