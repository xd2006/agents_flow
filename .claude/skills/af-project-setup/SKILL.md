---
name: af-project-setup
description: >-
  Game prototype setup, technical stack selection, and deployment coordinator skill. Use this skill
  when starting, planning, evaluating technical stacks, or deploying a game prototype. Discovers
  requirements, justifies stack choices, produces technical specifications and deployment plans,
  and executes gated deployments.
---

# AF-Project-SetUp Skill

This skill guides the agent in discovering game prototype requirements, selecting and justifying technical stacks, authoring approved technical specifications and deployment plans, and safely executing deployments under explicit phase gates.

## Master Agent Specification & Manual
Full instructions, operating rules, and templates are maintained in:
[AF-Project-SetUp Master Spec](file:///d:/mydocs/GitHub/Agent-Flow/Agents/AF-Project-SetUp/AF-Project-SetUp.md)

---

## Standard 3-Phase Execution Lifecycle

### Phase 1: Discovery
1. **Context & Inspection:**
   - Confirm project root, host runtime, and whether the project is new or existing.
   - Inspect existing manifests, dependencies, build files, and memory in [PROJECT_STATE.md](file:///d:/mydocs/GitHub/Agent-Flow/Agent_Memory/_Shared/PROJECT_STATE.md).
2. **Requirements Interview:**
   - Target platforms: browser, desktop, mobile (responsive web vs PWA vs APK/AAB vs iOS).
   - Core game loop, rendering (2D/3D), camera, physics, audio, effects, controls.
   - Persistence, backend, multiplayer, identity, APIs, AI services, analytics.
   - Operational constraints: performance, budget, hosting, deadlines.
   - Use `/roas-me` if available in runtime; otherwise use fallback structured interview.
3. **Produce Report:**
   - Author `docs/setup/DISCOVERY_REPORT.md`.
4. **Transition Gate:**
   - Ask user explicitly: *"Approve transition to Phase 2 — Planning?"*

### Phase 2: Planning & Preparation
1. **Stack Evaluation:**
   - Compare at least two viable stacks with evidence, trade-offs, and version compatibility.
2. **Author Specifications:**
   - Write `docs/setup/TECHNICAL_SPEC.md` (Scope, architecture, data flow, APIs, criteria).
   - Write `docs/setup/DEPLOYMENT_PLAN.md` (Ordered steps, preflight, gates, rollback, tests).
3. **Transition Gate:**
   - Both documents must be marked `PROPOSED`.
   - Ask user explicitly to approve both documents and authorize transition to Phase 3.

### Phase 3: Deployment
1. **Preflight:**
   - Inspect tools, OS, disk space, network, permissions; write `docs/setup/ENVIRONMENT_REPORT.md`.
2. **Gated Execution:**
   - Execute plan in bounded steps. Request confirmation for any high-risk, costly, or irreversible step.
   - Validate each step before advancing.
3. **Verification & Delivery:**
   - Run build/test/smoke checks; record actual outcomes.
   - Author `docs/setup/DEPLOYMENT_REPORT.md` with run/stop instructions.
   - Update durable memory under `Agent_Memory/AF-Project-SetUp/` and shared project state.
