# Decision Log — AF-Installer

## Decisions

### DEC-20261014-001: Consolidated Master Agent Architecture
- **Date:** 2026-10-14
- **Status:** CONFIRMED
- **Context:** The source package `AF-Intaller/` distributes instructions across 13 distinct files (system prompt, agent spec, workflow, 6 domain skills, 3 inherited skills, output contract, memory rules, QA checklist). The user requested creating the agent "with all instructions inside".
- **Decision:** Consolidate all 13 modules into a comprehensive single-file master specification at `Agents/AF-Installer/AF-Installer.md` while keeping the original modular files intact for reference.
- **Rationale:** Provides a fully self-contained agent prompt/spec that can be ported to any LLM runtime, while retaining complete adherence to every rule.
- **Affected Files:** `Agents/AF-Installer/AF-Installer.md`

### DEC-20261014-002: Runtime Adaptation to Google Antigravity
- **Date:** 2026-10-14
- **Status:** CONFIRMED
- **Context:** Active runtime detected as Google Antigravity. Antigravity discovers workspace customizations via `.agents/skills/<name>/SKILL.md` (YAML frontmatter) and rules via `AGENTS.md` / `.agents/rules/*.md`.
- **Decision:** Install AF-Installer as a native Antigravity skill at `.agents/skills/af-installer/SKILL.md` and define project governance in `AGENTS.md`.
- **Rationale:** Allows Antigravity to autonomously invoke AF-Installer whenever agent installation tasks are requested.
- **Affected Files:** `.agents/skills/af-installer/SKILL.md`, `AGENTS.md`, `.agents/rules/af-installer.md`
