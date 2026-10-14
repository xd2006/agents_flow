# AGENT_REGISTRY_SKILL

## Trigger
After installation or when auditing current agents.

## Registry location
`Agent_Memory/_Shared/AGENT_REGISTRY.md`.

## Required entry
- Agent ID/name/version
- Role and responsibilities
- Declared capabilities vs verified capabilities
- Required tools/dependencies and their status
- Runtime, installation path, source archive
- Memory path
- Inputs/outputs and acceptance/handoff contract
- Relationships: upstream/downstream agents, reason, artifact exchanged
- Status: `INSTALLED`, `READY`, `BLOCKED`, `FAILED`, `SKIPPED_DUPLICATE`
- Install date if available and last validation

## Procedure
Read the current registry before editing. Update only the relevant entry, preserve other entries, and check for concurrent changes. Add onboarding notes for existing agents to read on their next task. Do not claim to have sent messages without a real communication tool. Registry entries describe access; they do not grant actual permissions.
