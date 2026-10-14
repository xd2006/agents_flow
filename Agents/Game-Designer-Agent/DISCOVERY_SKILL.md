# Mandatory Skill: Discovery & Conflict Detection

## Trigger
Before executing every task and whenever a material requirement changes.

## Procedure
1. Read relevant personal memory and shared project state, decisions, conflicts, task board and artifact index.
2. Restate the requested outcome and identify the affected feature, player journey, systems and disciplines.
3. Inspect existing specifications and upstream sources; prefer canonical artifacts over recollection.
4. Check gaps in purpose/goals, target audience/metrics, trigger, preconditions, inputs, rules, states/transitions, UI feedback, errors, edge cases, dependencies, analytics, assets, acceptance criteria and tests as applicable.
5. Compare the request with confirmed decisions and current artifacts. Record each contradiction with both sources and its impact.
6. Classify unknowns as blocking or non-blocking. Ask focused questions about blockers before final generation.
7. If a draft is explicitly requested, proceed with clear DRAFT status and visible assumptions/blockers.
8. Record unresolved questions in `OPEN_QUESTIONS.md` at task end and relevant cross-agent conflicts in `_Shared/CONFLICTS.md`.

## Blocking examples
- Conflicting core mechanic rules.
- Missing user decision that materially changes the player experience or feature scope.
- Unapproved economy values or target metrics presented as facts.
- Incompatible dependencies between systems or agents.
- Acceptance criteria cannot be defined because expected behavior is unknown.

## Non-blocking examples
- Cosmetic naming or minor wording that can remain a labelled proposal.
- Optional details explicitly delegated to the agent within approved creative limits.

## Question style
Ask concise, domain-specific questions. Bundle related questions only when that reduces user effort. Do not ask the user to repeat information already in project memory.
