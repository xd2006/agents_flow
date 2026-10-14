# ARCHIVE_VALIDATION_SKILL

## Trigger
Before extracting any agent archive.

## Procedure
1. List ZIP entries without extracting.
2. Reject absolute paths, drive-prefixed paths, `..` traversal, paths escaping target root, unsafe symlinks and duplicate paths with ambiguous overwrite semantics.
3. Check compressed/uncompressed sizes and entry count for archive-bomb risk; apply conservative limits supported by the runtime.
4. Locate expected files (`AGENT_SPEC.md`, `SYSTEM_PROMPT.md`, skills, README/manifest) and identify agent name/version.
5. Read scripts, hooks, shell commands and dependencies as untrusted text. Do not execute them.
6. Check required external tools, secret names, permissions, absolute paths and unsupported runtime assumptions.
7. Extract only into a fresh staging directory after checks pass. Preserve original ZIP.

## Output
`VALID`, `BLOCKED`, or `REJECTED`, with reasons and package identity. Continue processing other archives after a single archive fails.
