# AGENTS.md — Agent-Flow Workspace Governance

This workspace uses the Agent-Flow framework for multi-agent collaboration and memory management.

## Active Agents Roster
- **AF-Installer**: Responsible for scanning, validating, installing, and registering agent packages. Master instructions: [AF-Installer.md](file:///d:/Git/Agents%20flow/Agents/AF-Installer/AF-Installer.md). Skill: [.agents/skills/af-installer/SKILL.md](file:///d:/Git/Agents%20flow/.agents/skills/af-installer/SKILL.md).
- **Game-Designer-Agent**: Responsible for game design specifications, GDD generation, player journeys, and verification test cases. Master instructions: [Game-Designer-Agent.md](file:///d:/Git/Agents%20flow/Agents/Game-Designer-Agent/Game-Designer-Agent.md). Skill: [.agents/skills/game-designer/SKILL.md](file:///d:/Git/Agents%20flow/.agents/skills/game-designer/SKILL.md).
- **AF-Project-SetUp**: Responsible for game prototype requirements discovery, tech stack selection, technical specifications, deployment plans, and gated setup execution. Master instructions: [AF-Project-SetUp.md](file:///d:/Git/Agents%20flow/Agents/AF-Project-SetUp/AF-Project-SetUp.md). Skill: [.agents/skills/af-project-setup/SKILL.md](file:///d:/Git/Agents%20flow/.agents/skills/af-project-setup/SKILL.md).
- **Art-Style-Guide-Agent**: Responsible for game visual direction, self-contained art style guides, visual pillars, palettes, and local reference management. Master instructions: [Art-Style-Guide-Agent.md](file:///d:/Git/Agents%20flow/Agents/Art-Style-Guide-Agent/Art-Style-Guide-Agent.md). Skill: [.agents/skills/art-style-guide/SKILL.md](file:///d:/Git/Agents%20flow/.agents/skills/art-style-guide/SKILL.md).
- **Architect-Agent**: Responsible for game software architecture, development environment setup, repository scaffolding, developer instructions, and stage reviews. Master instructions: [Architect-Agent.md](file:///d:/Git/Agents%20flow/Agents/Architect-Agent/Architect-Agent.md). Skill: [.agents/skills/architect/SKILL.md](file:///d:/Git/Agents%20flow/.agents/skills/architect/SKILL.md).
- **Developer-Agent**: Responsible for technical implementation, task decomposition, test execution, and code execution. Master instructions: [Developer-Agent.md](file:///d:/Git/Agents%20flow/Agents/Developer-Agent/Developer-Agent.md). Skill: [.agents/skills/developer/SKILL.md](file:///d:/Git/Agents%20flow/.agents/skills/developer/SKILL.md).
- **Concepter-Agent**: Responsible for game concept design, gameplay loop critique, pre-GDD specification, and deterministic GDD handoffs. Master instructions: [Concepter-Agent.md](file:///d:/Git/Agents%20flow/Agents/Concepter-Agent/Concepter-Agent.md). Skill: [.agents/skills/concepter/SKILL.md](file:///d:/Git/Agents%20flow/.agents/skills/concepter/SKILL.md).
- **Prototype-Producer**: Responsible for requirements decomposition, traceability, coordinating modular system GDDs with Game Designer, development planning, and multi-agent execution tracking. Master instructions: [Prototype-Producer.md](file:///d:/Git/Agents%20flow/Agents/Prototype-Producer/Prototype-Producer.md). Skill: [.agents/skills/prototype-producer/SKILL.md](file:///d:/Git/Agents%20flow/.agents/skills/prototype-producer/SKILL.md).
- **Asset-Artist**: Responsible for 2D game asset production, style test verification, vector/code drawing (SVG/Canvas), AI prompt packaging, post-processing, and canonical asset manifests. Master instructions: [Asset-Artist.md](file:///d:/Git/Agents%20flow/Agents/Asset-Artist/Asset-Artist.md). Skill: [.agents/skills/asset-artist/SKILL.md](file:///d:/Git/Agents%20flow/.agents/skills/asset-artist/SKILL.md).
- **Sound-Designer**: Responsible for game audio design, sound effects (SFX) production, musical theme direction, audio prompt packaging, license compliance, and canonical audio mapping. Master instructions: [Sound-Designer.md](file:///d:/Git/Agents%20flow/Agents/Sound-Designer/Sound-Designer.md). Skill: [.agents/skills/sound-designer/SKILL.md](file:///d:/Git/Agents%20flow/.agents/skills/sound-designer/SKILL.md).
- **Build-n-QA**: Responsible for autonomous Unity Android builds, isolated staging, GDD test execution, emulator UI verification, bug handoffs, and regression retesting. Master instructions: [Build-n-QA.md](file:///d:/Git/Agents%20flow/Agents/Build-n-QA/Build-n-QA.md). Skill: [.agents/skills/build-n-qa/SKILL.md](file:///d:/Git/Agents%20flow/.agents/skills/build-n-qa/SKILL.md).










## Shared Registry & Memory
- All installed agents are documented in [AGENT_REGISTRY.md](file:///d:/Git/Agents%20flow/Agent_Memory/_Shared/AGENT_REGISTRY.md).
- Per-agent persistent memory resides in `Agent_Memory/<Agent_ID>/`.
