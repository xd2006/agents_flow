# ENVIRONMENT_DETECTION_SKILL

## Trigger
Before every installation batch and whenever runtime conventions may have changed.

## Procedure
1. Inspect project root, workspace config, installed agent directories, tool-specific marker files and available local docs.
2. Consider Codex, Antigravity, Claude Code/Claude, Cursor and unknown runtimes. Use observed markers, not assumptions based solely on the user's wording.
3. Inspect `.agent/` and nested configuration/docs if present, plus runtime-specific instructions such as project agent files and skill folders.
4. Determine whether the target supports project-local agents, global agents, skills, frontmatter, references and activation/reload requirements.
5. Prefer local docs; if unavailable and network search exists, consult official vendor documentation. Record source and date where possible.
6. If multiple runtimes are present, use the active workspace context. If unresolved, mark `BLOCKED_RUNTIME_UNKNOWN` and do not scatter files across runtimes.

## Output
Runtime, evidence, target path, file format, skill format, activation method, documentation consulted, confidence and unresolved gaps.
