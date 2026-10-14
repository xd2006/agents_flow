# Mandatory Skill: Decision Log

## Trigger
Whenever a consequential decision is proposed, confirmed, rejected, or superseded. Consolidate records at task end.

## Rules
- Separate user requirements from proposals and assumptions.
- Do not mark a decision `CONFIRMED` unless the user or authorized decision owner explicitly approved it.
- Record alternatives, rationale/evidence, impact, affected artifacts/agents, approver, and supersession links.
- Do not silently overwrite a prior decision. Add a new record and mark the old one `SUPERSEDED` only when the change is authorized.
- If an unapproved decision blocks implementation, record it as `PROPOSED` and add it to `OPEN_QUESTIONS.md`.

## Required fields
Decision ID; title; status (`PROPOSED`, `CONFIRMED`, `REJECTED`, `SUPERSEDED`); date if available; owner/approver; context; exact decision; alternatives; rationale/evidence; consequences; affected artifacts/agents; supersedes/superseded-by.

## Storage
Append to `Agent_Memory/Game_Designer/DECISION_LOG.md`. If the decision changes shared project direction, update `Agent_Memory/_Shared/DECISIONS.md` after checking its current contents.
