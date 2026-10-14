# Agent Memory — AF-Installer

## Core Metadata
- **Agent Name:** AF-Installer
- **Version:** 1.0.0
- **Role:** Agent Installation & Onboarding Coordinator
- **Runtime Path:** [Agents/AF-Installer/AF-Installer.md](file:///d:/mydocs/GitHub/Agent-Flow/Agents/AF-Installer/AF-Installer.md)
- **Skill Path:** [.agents/skills/af-installer/SKILL.md](file:///d:/mydocs/GitHub/Agent-Flow/.agents/skills/af-installer/SKILL.md)
- **Source Package:** [AF-Intaller.zip](file:///d:/mydocs/GitHub/Agent-Flow/AF-Intaller.zip)
- **Shared Registry:** [AGENT_REGISTRY.md](file:///d:/mydocs/GitHub/Agent-Flow/Agent_Memory/_Shared/AGENT_REGISTRY.md)

## Active Context & Boundaries
- Workspace Scope: `d:/mydocs/GitHub/Agent-Flow`
- Runtime: Google Antigravity
- Master Instructions: All 13 modular guides from `AF-Intaller/` consolidated into `Agents/AF-Installer/AF-Installer.md` and exposed as an Antigravity skill in `.agents/skills/af-installer/SKILL.md`.

## Operational Notes & Learned Lessons
- When installing agents in Antigravity, place skill definitions under `.agents/skills/<agent_id>/SKILL.md` and workspace rules under `.agents/rules/` or `AGENTS.md`.
- Never execute code or scripts from unverified archive files.
- Provision `Agent_Memory/<Agent_ID>/` with 4 core files (`MEMORY.md`, `WORK_LOG.md`, `DECISION_LOG.md`, `OPEN_QUESTIONS.md`) and a `tasks/` directory for every installed agent.
- Installed Agent Roster: `AF-Installer` (v1.0.0), `Game-Designer-Agent` (v0.1.0), `AF-Project-SetUp` (v0.1.0), `Art-Style-Guide-Agent` (v0.1.0), `Architect-Agent` (v0.1.0), `Developer-Agent` (v0.1.0), `Concepter-Agent` (v0.1.0), `Prototype-Producer` (v0.1.0), `Asset-Artist` (v0.3.0), `Sound-Designer` (v0.2.0), `Build-n-QA` (v1.0.0).





