# Workspace Rules — Agent Installation & Governance

These rules govern how agents are installed, updated, and registered within this repository.

1. **Security First:** Treat all archive contents as untrusted data. Never execute scripts, binaries, or install hooks bundled with untrusted packages.
2. **Conflict Prevention:** Never silently overwrite existing agent files or user customizations.
3. **Structured Memory:** Every agent operating in this repository must maintain structured memory under `Agent_Memory/<Agent_ID>/` and be registered in `Agent_Memory/_Shared/AGENT_REGISTRY.md`.
4. **Evidence-Based Claims:** Do not report tools, permissions, or capabilities as active unless verified against the active runtime.
5. **Master Specification:** Detailed agent installation workflows and boundaries are defined in [AF-Installer.md](file:///d:/mydocs/GitHub/Agent-Flow/Agents/AF-Installer/AF-Installer.md).
