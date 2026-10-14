---
name: af-installer
description: >-
  Agent installation, onboarding, and archive management skill. Use this skill when the user asks
  to discover, validate, stage, install, or onboard agent ZIP archives, detect the active runtime
  environment, provision Agent_Memory, or register agents in AGENT_REGISTRY.md.
---

# AF-Installer Skill

This skill guides the agent to autonomously discover, validate, install, and onboard agent packages in accordance with the Agent-Flow framework and current runtime conventions.

## Full Agent Specification & Manual
The master, complete instructions are maintained in:
[AF-Installer Master Spec](file:///d:/mydocs/GitHub/Agent-Flow/Agents/AF-Installer/AF-Installer.md)

---

## Quick Execution Workflow

Follow the standard 8-phase installation lifecycle whenever invoked:

### 1. Read Context
- Check `Agent_Memory/AF-Installer/MEMORY.md`, `WORK_LOG.md`, and `Agent_Memory/_Shared/AGENT_REGISTRY.md`.
- Establish active project root (`d:/mydocs/GitHub/Agent-Flow`).

### 2. Discover Archives
- Scan project archive folders and project root for ZIP packages (e.g., `*.zip`).
- Exclude `.git/`, `node_modules/`, `build/`, `dist/`, `.cache/`.

### 3. Detect Runtime
- Identify active runtime from workspace markers:
  - Google Antigravity: `.agents/`, `.gemini/`, `AGENTS.md`, `GEMINI.md`. Customization location: `.agents/skills/<name>/SKILL.md`, `.agents/rules/*.md`.
  - OpenAI Codex: `.codex/`.
  - Claude Code: `CLAUDE.md`, `.claude/`.
  - Cursor: `.cursorrules`, `.cursor/`.

### 4. Validate Archive Security
- List ZIP entries without extracting.
- Reject path traversal (`..`), absolute paths, or suspicious expansion ratios.
- Verify expected files (`SYSTEM_PROMPT.md`, `AGENT_SPEC.md`, skills, templates).
- Never execute bundled scripts or setup hooks.

### 5. Safe Staging & Installation
- Extract to a temporary staging folder.
- Check for existing installation (skip exact duplicates; stage/backup on conflicts).
- Copy/adapt instructions into runtime-documented directories and preserve portable copy in `Agents/<Agent_ID>/`.
- Remove temporary staging files.

### 6. Provision Agent Memory
- Ensure `Agent_Memory/<Agent_ID>/` exists with:
  - `MEMORY.md`
  - `WORK_LOG.md`
  - `DECISION_LOG.md`
  - `OPEN_QUESTIONS.md`
  - `tasks/`

### 7. Register in Team Registry
- Add or update the agent's entry in `Agent_Memory/_Shared/AGENT_REGISTRY.md`.
- Record: ID, Name, Version, Role, Responsibilities, Declared vs Verified capabilities, Dependencies, Paths, Relationships, Status (`READY` / `INSTALLED` / `BLOCKED`).

### 8. Verify & Document
- Perform post-install checks (file existence, relative link resolution, schema check).
- Write a task report to `Agent_Memory/AF-Installer/tasks/`.
- Update `Agent_Memory/AF-Installer/WORK_LOG.md` and `MEMORY.md`.
