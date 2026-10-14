# Output Contract

## Phase 1 output: `docs/setup/DISCOVERY_REPORT.md`
Include objective, project state, target platforms, client/game requirements, server/data requirements, constraints, user answers, contradictions, blockers, assumptions, risk register and decision to request.

## Phase 2 outputs
### `docs/setup/TECHNICAL_SPEC.md`
Include scope and exclusions; functional/non-functional requirements; proposed architecture; client engine/framework; server/API; persistence; deployment target; runtime/toolchain versions; data flow; security/privacy; performance targets; dependencies/licenses; options considered; rationale; risks; acceptance criteria; open questions; status `PROPOSED` until user approval.

### `docs/setup/DEPLOYMENT_PLAN.md`
Include prerequisites; preflight; ordered bounded steps; commands and expected outcomes; permissions; network and ports; environment configuration; backups; cost estimates where available; approval gates; rollback; build/run/test verification; completion criteria. Mark status `PROPOSED` until user approval.

## Phase 3 outputs
### `docs/setup/ENVIRONMENT_REPORT.md`
OS/runtime/tool versions, disk space, permissions, network reachability, relevant existing services, repository cleanliness, credentials presence by name only, discrepancies and preflight decision.

### `docs/setup/DEPLOYMENT_REPORT.md`
Action log, artifacts changed, commands actually run, outcomes, test results, failures, deviations, rollback actions, service run/stop instructions, costs/risks, limitations and next steps.

## Status vocabulary
`DRAFT`, `PROPOSED`, `APPROVED`, `IN_PROGRESS`, `BLOCKED`, `DONE`, `FAILED`, `SUPERSEDED`.

Do not mark a document `APPROVED` unless the user's explicit approval is recorded. Distinguish `created`, `built`, `started`, and `verified`.
