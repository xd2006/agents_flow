# Workflow

## Phase 1 — Discovery
**Entry:** User asks to set up a game prototype or prepare an existing game project.
1. Establish project root and actual runtime/editor. If unclear, ask one direct question.
2. Inspect documentation, repository status, folder structure, manifests, existing build scripts, runtime versions, and relevant project memory. Do not dump secrets into reports.
3. Identify whether the project is new or existing and summarize current technical state.
4. Extract requirements already documented. Detect contradictions, stale docs and missing decisions.
5. Interview the user about target platform (browser/phone/desktop), web vs APK/AAB/iOS package, game genre and prototype goal, scenes, visual effects, controls, input devices, performance, offline use, persistence, identity, multiplayer, backend/API/AI needs, analytics, data sensitivity, scale, budget and deadlines as relevant.
6. Use `/roas-me` if actually available; otherwise use the domain interview skill.
7. Produce a discovery report with requirements, constraints, unknowns, risks and blockers.
8. Present the report and request explicit approval to move to Phase 2.

**Exit criteria:** Requirements are sufficiently clear to compare stacks; critical blockers resolved or explicitly accepted as blockers for planning. User approves transition.

## Phase 2 — Planning and preparation
**Entry:** Phase 1 exit criteria met and user approved transition.
1. Compare at least two reasonable stacks when there are meaningful alternatives; one may be enough if constraints decisively dictate it, with explanation.
2. Evaluate client engine/framework, rendering, input, server/API, persistence, hosting, packaging, build pipeline, testing, security, licensing, support maturity, cost and developer iteration speed as applicable.
3. Recommend a stack with rationale, tradeoffs, risks, versions/compatibility evidence and alternatives.
4. Write `docs/setup/TECHNICAL_SPEC.md` including scope, architecture, components, data model, API/integration boundaries, target platforms, runtime/build versions, security/privacy, acceptance criteria, out-of-scope and open questions.
5. Write `docs/setup/DEPLOYMENT_PLAN.md` with ordered steps, prerequisites, exact commands where appropriate, permission needs, checkpoints, risks, rollback, verification and estimated cost where known.
6. Classify actions as autonomous low-risk, approval-required, or prohibited without additional authorization.
7. Review both documents for consistency and present them to the user. Ask for explicit approval of both documents and transition to Phase 3.
8. Incorporate requested revisions and resubmit; no deployment until approval is unambiguous.

**Exit criteria:** Technical specification and deployment plan both explicitly approved. Any unknown that affects architecture, cost, data loss, security or deployment target must be resolved or clearly bounded and approved.

## Phase 3 — Deployment
**Entry:** Both approved documents exist and the user explicitly approved transition.
1. Preflight: inspect available permissions/tools; OS/runtime versions; disk free space; network; package managers; ports; existing services; environment variables by name only; credentials presence without printing values; repository cleanliness; backups; target services and expected costs.
2. Write `docs/setup/ENVIRONMENT_REPORT.md`. If preflight exposes a material discrepancy, stop and return to Phase 2 for plan revision.
3. Execute the plan in bounded steps. Before each risky, irreversible, privileged, costly or externally visible operation, request action-specific confirmation. Low-risk, reversible actions may proceed autonomously.
4. Keep changes scoped. Prefer local/project-scoped dependencies and lockfiles. Do not expose services publicly by default.
5. After each meaningful stage, validate the expected result. Stop on unexpected destructive effects, permission escalation, cost changes, credential exposure, unexplained environment differences, or material deviation from plan.
6. For failures, capture sanitized logs, diagnose, attempt only safe reversible recovery, and ask before risky rollback or data-changing repair.
7. Run relevant format/lint/unit/build/smoke checks and launch the project where possible. Record exact commands and outcomes.
8. Write `docs/setup/DEPLOYMENT_REPORT.md`; update task state, decision log and artifact index.
9. Summarize deployed components, how to run/stop them, validation results, known limitations, cost implications, rollback and next steps.

**Exit criteria:** Approved scope deployed and verified as far as the environment permits; all unrun checks, failures and remaining blockers explicitly listed.

## Return-to-planning rule
Any stack change, architecture change, deployment target change, data model migration, new paid resource, new external exposure, or action beyond the approved plan requires a pause, impact summary, plan/spec revision and user approval before proceeding.
