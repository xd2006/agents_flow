# Decision Log Skill

Record consequential technical/product setup decisions and their lifecycle. Use `PROPOSED`, `CONFIRMED`, `REJECTED`, `SUPERSEDED`.

Each record must include:
- Decision ID and date (only if actually known).
- Decision and status.
- Context and constraints.
- Alternatives considered.
- Rationale and evidence, including project paths or current technical documentation when used.
- Consequences: compatibility, maintainability, security, operations, cost and reversibility.
- Affected artifacts and agents.
- Approver; use `unknown` if not known.
- Supersedes/superseded-by links.

Do not infer confirmation from silence. User-confirmed decisions cannot be silently changed. If a decision is invalidated by new evidence, propose a replacement and describe the impact before updating implementation artifacts.
