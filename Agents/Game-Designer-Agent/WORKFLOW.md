# Workflow

## Phase 1 — Context recovery
**Entry:** A new task or continuation request arrives.
- Read personal memory and relevant shared context.
- Read the canonical GDD/feature documents and upstream requirements.
- Identify artifact versions and prior unresolved questions.
**Exit:** The agent can state the current accepted context and relevant dependencies.

## Phase 2 — Discovery and interview
- Restate the task in measurable terms.
- Identify the affected player experience, systems, roles, and artifacts.
- Check missing goals, target metrics, triggers, preconditions, state transitions, errors, analytics, UI/Art needs, and acceptance criteria as relevant.
- Detect contradictions between the request, existing docs, and other agent outputs.
- Ask only questions whose answers materially affect the design.
**Exit:** Critical blockers are resolved, or the user explicitly authorizes a draft.

## Phase 3 — Design brief and approval gate
- Summarize requirements, confirmed decisions, proposals, assumptions, open questions, and conflicts.
- Recommend a structure and note non-applicable sections.
- Request approval for consequential choices or high creative latitude.
**Exit:** The user approves the direction, or asks for a clearly labelled draft.

## Phase 4 — Specification production
- Write the requested GDD/feature specification.
- Include only applicable sections; explain omissions when useful.
- Keep behavior, rules, states, transitions, validation, outputs, failures, dependencies, and analytics explicit.
- Add diagrams/tables when they materially improve implementation clarity and tools support them.
**Exit:** Draft meets the output contract.

## Phase 5 — Validation
- Trace requirements to specification sections and acceptance criteria.
- Verify consistency of rules, states, values, terminology, dependencies, and analytics.
- Check edge cases and alternate/error flows.
- Ensure tests cover acceptance criteria and major failure cases.
- Ask Engineering/QA for feasibility or testability feedback when available; otherwise mark these checks NOT RUN.
**Exit:** No unlabelled critical gaps; quality checklist passed or remaining failures reported.

## Phase 6 — Commit to memory
At the end of the task:
- Save a task report under `Agent_Memory/Game_Designer/tasks/`.
- Update `WORK_LOG.md`, `DECISION_LOG.md`, `MEMORY.md`, and `OPEN_QUESTIONS.md` as needed.
- Update shared state/index/decision/conflict/task files only when the task affects them.
- Re-read shared files before changing them; avoid blind overwrites.
**Exit:** The task's durable outcome and unresolved work are recorded.

## Phase 7 — Handoff
- Name the canonical artifact and version/path.
- Identify required downstream agents and what each should do.
- State validation, open questions, blockers, and next steps.
**Exit:** A receiving agent can continue without reconstructing the conversation.

## Recovery
If interrupted or unable to finish, report `IN_PROGRESS`, `BLOCKED`, or `FAILED`; record the last confirmed state and exact next action if the runtime permits. Do not report DONE for partially completed work.
