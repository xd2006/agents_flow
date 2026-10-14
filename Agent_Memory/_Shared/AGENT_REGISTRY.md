# Agent Registry

> This registry describes the agent roster. It does not itself grant OS, filesystem, network, credential, or tool permissions.

## Agents

### AF-Installer
- **Name:** AF-Installer
- **Version:** 1.0.0
- **Role:** Agent Installation & Onboarding Coordinator
- **Responsibilities:**
  - Discover agent ZIP archives across project search paths.
  - Detect active runtime environment and inspect documentation.
  - Safely validate, stage, and install agent packages.
  - Provision `Agent_Memory` structures and maintain `AGENT_REGISTRY.md`.
  - Perform post-install QA verification.
- **Declared capabilities:** ZIP archive extraction, filesystem analysis, runtime detection, agent registration, onboarding coordination.
- **Verified capabilities:** Filesystem read/write, terminal execution (PowerShell), archive inspection (`tar`, `Expand-Archive`), Antigravity skill activation.
- **Required tools/dependencies:** Filesystem read/write, ZIP inspection/extraction tools.
- **Dependency status:** SATISFIED
- **Runtime:** Google Antigravity
- **Install path:** [Agents/AF-Installer/AF-Installer.md](file:///d:/Git/Agents%20flow/Agents/AF-Installer/AF-Installer.md) / [.agents/skills/af-installer/SKILL.md](file:///d:/Git/Agents%20flow/.agents/skills/af-installer/SKILL.md)
- **Source archive:** [AF-Intaller.zip](file:///d:/Git/Agents%20flow/AF-Intaller.zip)
- **Memory path:** [Agent_Memory/AF-Installer/](file:///d:/Git/Agents%20flow/Agent_Memory/AF-Installer)
- **Inputs:** Agent ZIP archives, runtime documentation, project configuration.
- **Outputs:** Installed agent instructions, provisioned memory structures, task reports, registry records.
- **Relationships:**
  - Upstream: User requests, archive maintainers
  - Downstream: Newly onboarded agents (e.g., Game-Designer-Agent)
- **Handoff contract:** Receives agent packages for installation; produces registered agents ready for operation.
- **Status:** READY
- **Last validation:** 2026-10-14
- **Notes / blockers:** Fully installed with consolidated master specification and Antigravity skill integration.

### Game-Designer-Agent
- **Name:** Game-Designer-Agent
- **Version:** 0.1.0
- **Role:** Game Design Documentation & Systems Specification Specialist
- **Responsibilities:**
  - Elicit, structure, and refine game feature and system requirements.
  - Identify missing info, contradictions, dependencies, edge cases, and technical risks.
  - Produce implementation-ready GDD sections and feature specs.
  - Define player journeys, state transitions, acceptance criteria, and traceable test cases.
- **Declared capabilities:** GDD generation, user journey mapping, acceptance criteria specification, game mechanics design, test case creation.
- **Verified capabilities:** Static Markdown GDD generation, Mermaid diagramming, structured spec review. (External DOCX export / image generation unverified).
- **Required tools/dependencies:** Filesystem read/write for GDD markdown files, access to `Agent_Memory/`.
- **Dependency status:** SATISFIED
- **Runtime:** Google Antigravity
- **Install path:** [Agents/Game-Designer-Agent/Game-Designer-Agent.md](file:///d:/Git/Agents%20flow/Agents/Game-Designer-Agent/Game-Designer-Agent.md) / [.agents/skills/game-designer/SKILL.md](file:///d:/Git/Agents%20flow/.agents/skills/game-designer/SKILL.md)
- **Source archive:** [game-designer-agent.zip](file:///d:/Git/Agents%20flow/game-designer-agent.zip)
- **Memory path:** [Agent_Memory/Game-Designer-Agent/](file:///d:/Git/Agents%20flow/Agent_Memory/Game-Designer-Agent)
- **Inputs:** User brief, design requirements, feedback, constraints, peer agent reports.
- **Outputs:** Game Design Documents (GDDs), feature specifications, flowcharts, acceptance criteria, test cases.
- **Relationships:**
  - Upstream: User / Product Owner, Production Agent
  - Downstream: Developer Agent, Art Agent, UI/UX Agent, QA Agent, Analytics Agent
- **Handoff contract:** Receives feature goals and constraints; delivers complete GDD with acceptance criteria and test cases.
- **Status:** READY
- **Last validation:** 2026-10-14
- **Notes / blockers:** Fully installed and activated. Ready for design tasks via skill `/game-designer`.

### AF-Project-SetUp
- **Name:** AF-Project-SetUp
- **Version:** 0.1.0
- **Role:** Game Prototype Project Setup & Deployment Coordinator
- **Responsibilities:**
  - Inspect project documentation, codebases, manifests, and memory before planning.
  - Conduct structured discovery interview on target platforms, rendering, controls, persistence, backend, and budget.
  - Formulate and compare viable tech stacks with trade-offs and compatibility rationale.
  - Produce implementation-ready `TECHNICAL_SPEC.md` and actionable `DEPLOYMENT_PLAN.md`.
  - Enforce explicit user approval gates between Discovery, Planning, and Deployment phases.
  - Execute preflight environmental checks and gated, reversible deployments.
  - Maintain durable logs and truthful execution reporting.
- **Declared capabilities:** Cross-environment project setup, stack evaluation, tech spec authoring, deployment planning, gated execution, environment preflight.
- **Verified capabilities:** Filesystem read/write, terminal execution (PowerShell), markdown spec generation, Antigravity skill activation. (Third-party cloud provisioning / external deployment tools unverified).
- **Required tools/dependencies:** Filesystem read/write, terminal shell for deployment commands, access to `Agent_Memory/`.
- **Dependency status:** SATISFIED
- **Runtime:** Google Antigravity
- **Install path:** [Agents/AF-Project-SetUp/AF-Project-SetUp.md](file:///d:/Git/Agents%20flow/Agents/AF-Project-SetUp/AF-Project-SetUp.md) / [.agents/skills/af-project-setup/SKILL.md](file:///d:/Git/Agents%20flow/.agents/skills/af-project-setup/SKILL.md)
- **Source archive:** [af-project-setup.zip](file:///d:/Git/Agents%20flow/af-project-setup.zip)
- **Memory path:** [Agent_Memory/AF-Project-SetUp/](file:///d:/Git/Agents%20flow/Agent_Memory/AF-Project-SetUp)
- **Inputs:** User requirements, existing repository files, GDDs from Game-Designer-Agent, environment configuration.
- **Outputs:** `docs/setup/DISCOVERY_REPORT.md`, `docs/setup/TECHNICAL_SPEC.md`, `docs/setup/DEPLOYMENT_PLAN.md`, `docs/setup/ENVIRONMENT_REPORT.md`, `docs/setup/DEPLOYMENT_REPORT.md`.
- **Relationships:**
  - Upstream: User / Product Owner, Game-Designer-Agent (for GDD inputs)
  - Downstream: Developer Agent, QA Agent, DevOps / Deployment tooling
- **Handoff contract:** Receives game requirements or GDD; delivers approved technical specification, deployment plan, and executed environment setup.
- **Status:** READY
- **Last validation:** 2026-10-14
- **Notes / blockers:** Fully installed and activated. Ready for setup tasks via skill `/af-project-setup`.

### Art-Style-Guide-Agent
- **Name:** Art-Style-Guide-Agent
- **Version:** 0.1.0
- **Role:** Game Visual Direction & Art Style Guide Specialist
- **Responsibilities:**
  - Inspect project instructions, concept documents, and visual guidelines.
  - Extract visual style requirements, color palettes, lighting, silhouettes, and existing references.
  - Enforce the strict reference rule: references originate exclusively from concept doc or user upload (no web search, no AI generation).
  - Produce self-contained, implementation-ready art style guides in Markdown.
  - Organize and validate local reference files in adjacent `references/` folders with relative links.
  - Define visual style boundaries, "Do's and Don'ts", and review criteria.
  - Maintain durable records under `Agent_Memory/Art-Style-Guide-Agent/`.
- **Declared capabilities:** Art style guide authoring, visual reference organization, aesthetic requirement extraction, style boundary definition.
- **Verified capabilities:** Filesystem read/write, markdown guide generation, local relative reference linking, Antigravity skill activation. (Image viewing/rendering capability unverified without multimodal runtime tools).
- **Required tools/dependencies:** Filesystem read/write for markdown documents and reference files, access to `Agent_Memory/`.
- **Dependency status:** SATISFIED
- **Runtime:** Google Antigravity
- **Install path:** [Agents/Art-Style-Guide-Agent/Art-Style-Guide-Agent.md](file:///d:/Git/Agents%20flow/Agents/Art-Style-Guide-Agent/Art-Style-Guide-Agent.md) / [.agents/skills/art-style-guide/SKILL.md](file:///d:/Git/Agents%20flow/.agents/skills/art-style-guide/SKILL.md)
- **Source archive:** [art-style-guide-agent.zip](file:///d:/Git/Agents%20flow/art-style-guide-agent.zip)
- **Memory path:** [Agent_Memory/Art-Style-Guide-Agent/](file:///d:/Git/Agents%20flow/Agent_Memory/Art-Style-Guide-Agent)
- **Inputs:** User brief, game concept document, visual requirements, user-provided reference files.
- **Outputs:** `docs/art/ART_STYLE_GUIDE.md`, local `references/` files, task execution reports.
- **Relationships:**
  - Upstream: User / Product Owner, Game-Designer-Agent (concept & design docs)
  - Downstream: Art Team, 3D/2D Artists, UI/UX Designer, Tech Artist
- **Handoff contract:** Receives visual concept or design doc; delivers comprehensive art style guide and verified local references.
- **Status:** READY
- **Last validation:** 2026-10-14
- **Notes / blockers:** Fully installed and activated. Ready for visual direction tasks via skill `/art-style-guide`.

### Architect-Agent
- **Name:** Architect-Agent
- **Version:** 0.1.0
- **Role:** Game System Architecture, Development Environment & Developer Instructions Specialist
- **Responsibilities:**
  - Design software architecture, system modules, scene flows, and state management.
  - Define integration pipelines for art assets and audio.
  - Organize and scaffold repository structures, `.gitignore`, and configuration templates.
  - Specify reproducible development environments and setup commands (`ENVIRONMENT.md`).
  - Author structured developer instructions with stage goals, acceptance criteria, and checkpoints (`DEV_INSTRUCTIONS.md`).
  - Conduct stage reviews and evaluate completion criteria (`Stage Review`).
  - Facilitate inter-agent communication and question handling via mailbox (`_Mailbox/`).
  - Maintain durable records under `Agent_Memory/Architect-Agent/`.
- **Declared capabilities:** Software architecture design, environment specification, repository scaffolding, developer instruction authoring, stage completion auditing, mailbox-based peer coordination.
- **Verified capabilities:** Filesystem read/write, markdown spec generation, terminal execution (PowerShell), Antigravity skill activation. (Automated headless build/run verification tools unverified).
- **Required tools/dependencies:** Filesystem read/write, terminal execution for environment verification, access to `Agent_Memory/`.
- **Dependency status:** SATISFIED
- **Runtime:** Google Antigravity
- **Install path:** [Agents/Architect-Agent/Architect-Agent.md](file:///d:/Git/Agents%20flow/Agents/Architect-Agent/Architect-Agent.md) / [.agents/skills/architect/SKILL.md](file:///d:/Git/Agents%20flow/.agents/skills/architect/SKILL.md)
- **Source archive:** [architect-agent.zip](file:///d:/Git/Agents%20flow/architect-agent.zip)
- **Memory path:** [Agent_Memory/Architect-Agent/](file:///d:/Git/Agents%20flow/Agent_Memory/Architect-Agent)
- **Inputs:** Technical stack (`docs/setup/TECHNICAL_SPEC.md`), GDDs (`Game-Designer-Agent`), art style guides (`Art-Style-Guide-Agent`), Developer queries.
- **Outputs:** `docs/ARCHITECTURE.md`, `docs/ENVIRONMENT.md`, `docs/DEV_INSTRUCTIONS.md`, stage review reports, repository scaffolding, mailbox responses.
- **Relationships:**
  - Upstream: User / Product Owner, AF-Project-SetUp (tech stack), Game-Designer-Agent (GDD)
  - Downstream: Developer Agent (instructions, stage review), QA Agent
- **Handoff contract:** Receives tech stack and GDD; delivers approved architecture, configured repo environment, and staged developer instructions with verification gates.
- **Status:** READY
- **Last validation:** 2026-10-14
- **Notes / blockers:** Fully installed and activated. Ready for architecture and developer instruction tasks via skill `/architect`.

### Developer-Agent
- **Name:** Developer-Agent
- **Version:** 0.1.0
- **Role:** Technical Implementation & Code Execution Specialist
- **Responsibilities:**
  - Study technical stack, architecture, requirements, and section plans before coding.
  - Decompose implementation sections into atomic, testable tasks with clear acceptance criteria.
  - Formulate versioned implementation plans (`Plan vX`) and enforce the mandatory user approval gate.
  - Execute approved tasks sequentially with minimal, scoped code diffs.
  - Execute automated tests and static checks, capturing verifiable execution evidence (`PASS`/`FAIL`/`NOT RUN`).
  - Escalate architectural discrepancies and contract ambiguities to Architect-Agent via mailbox (`_Mailbox/Architect/`).
  - Document completed tasks in memory and update shared task boards.
- **Declared capabilities:** Code implementation, automated test execution, static analysis, architectural escalation, atomic task planning.
- **Verified capabilities:** Filesystem read/write, markdown plan and report authoring, PowerShell command execution, Antigravity skill activation. (Language-specific compiler/test runner toolchains subject to installed environment).
- **Required tools/dependencies:** Filesystem read/write, terminal execution for building and testing, access to `Agent_Memory/`.
- **Dependency status:** SATISFIED
- **Runtime:** Google Antigravity
- **Install path:** [Agents/Developer-Agent/Developer-Agent.md](file:///d:/Git/Agents%20flow/Agents/Developer-Agent/Developer-Agent.md) / [.agents/skills/developer/SKILL.md](file:///d:/Git/Agents%20flow/.agents/skills/developer/SKILL.md)
- **Source archive:** [developer-agent.zip](file:///d:/Git/Agents%20flow/developer-agent.zip)
- **Memory path:** [Agent_Memory/Developer-Agent/](file:///d:/Git/Agents%20flow/Agent_Memory/Developer-Agent)
- **Inputs:** Architecture specification (`docs/ARCHITECTURE.md`), Developer instructions (`docs/DEV_INSTRUCTIONS.md`), user approvals, existing codebase.
- **Outputs:** Source code changes, unit/integration test suites, task implementation reports, stage review requests.
- **Relationships:**
  - Upstream: User / Product Owner, Architect-Agent (architecture & stage review)
  - Downstream: QA Agent, DevOps
- **Handoff contract:** Receives approved architecture and developer instructions; delivers implemented and verified features with task execution reports.
- **Status:** READY
- **Last validation:** 2026-10-14
- **Notes / blockers:** Fully installed and activated. Ready for implementation tasks via skill `/developer`.

### Concepter-Agent
- **Name:** Concepter-Agent
- **Version:** 0.1.0
- **Role:** Game Concept Design & Pre-GDD Specification Specialist
- **Responsibilities:**
  - Elicit and critically evaluate game concepts for Mobile or Steam/PC.
  - Conduct focused inquiry rounds to resolve critical game loop, platform, and audience unknowns.
  - Provide constructive criticism and propose alternatives for weak mechanics or mismatched business models.
  - Produce concise 2–3 page concept documents structured across 14 mandatory sections.
  - Author deterministic machine-readable `GDD_HANDOFF` YAML blocks for seamless transition to Game-Designer-Agent.
  - Maintain document status as `DRAFT` until explicit user approval is granted.
  - Maintain durable records under `Agent_Memory/Concepter-Agent/`.
- **Declared capabilities:** Game concept design, gameplay loop critique, pre-GDD specification, deterministic GDD handoff generation.
- **Verified capabilities:** Filesystem read/write, markdown concept authoring, YAML schema validation, Antigravity skill activation. (Web search / market research capability activated only upon direct user request).
- **Required tools/dependencies:** Filesystem read/write for concept documents, access to `Agent_Memory/`.
- **Dependency status:** SATISFIED
- **Runtime:** Google Antigravity
- **Install path:** [Agents/Concepter-Agent/Concepter-Agent.md](file:///d:/Git/Agents%20flow/Agents/Concepter-Agent/Concepter-Agent.md) / [.agents/skills/concepter/SKILL.md](file:///d:/Git/Agents%20flow/.agents/skills/concepter/SKILL.md)
- **Source archive:** [concepter-agent.zip](file:///d:/Git/Agents%20flow/concepter-agent.zip)
- **Memory path:** [Agent_Memory/Concepter-Agent/](file:///d:/Git/Agents%20flow/Agent_Memory/Concepter-Agent)
- **Inputs:** Raw ideas, high concepts, target platform, user constraints, market research requests.
- **Outputs:** `docs/concept/CONCEPT_DOCUMENT.md` with embedded `GDD_HANDOFF` YAML block, critique reports.
- **Relationships:**
  - Upstream: User / Product Owner
  - Downstream: Game-Designer-Agent (receives GDD_HANDOFF to build full GDD), Art-Style-Guide-Agent (receives concept document)
- **Handoff contract:** Receives raw game idea; delivers approved 2–3 page concept document with valid `GDD_HANDOFF` YAML block.
- **Status:** READY
- **Last validation:** 2026-10-14
- **Notes / blockers:** Fully installed and activated. Ready for concept design tasks via skill `/concepter`.

### Prototype-Producer
- **Name:** Prototype-Producer
- **Version:** 0.1.0
- **Role:** Game Prototype Producer & Multi-Agent Development Coordinator
- **Responsibilities:**
  - Decompose game concept and environment constraints into a verifiable requirements registry (`REQUIREMENTS.md`).
  - Maintain end-to-end traceability from requirements to GDDs, tasks, and acceptance criteria (`TRACEABILITY.md`).
  - Coordinate modular system GDD authoring with Game-Designer-Agent and audit GDD coverage.
  - Autonomously return GDD gaps and contradictions to Game Designer for revision.
  - Package constructive design enhancements into `RECOMMENDATIONS.md` with scope/cost trade-offs for user decision.
  - Author comprehensive development plans (`DEVELOPMENT_PLAN.md`) with ordered tasks and verification gates.
  - Enforce the separate user launch command requirement prior to beginning development execution.
  - Track multi-agent task execution and verify agent reports in project memory.
- **Declared capabilities:** Prototype requirements decomposition, traceability management, multi-agent task orchestration, GDD review, development planning.
- **Verified capabilities:** Filesystem read/write, markdown spec generation, Antigravity skill activation, mailbox task coordination.
- **Required tools/dependencies:** Filesystem read/write for requirements and planning files, access to `Agent_Memory/`.
- **Dependency status:** SATISFIED
- **Runtime:** Google Antigravity
- **Install path:** [Agents/Prototype-Producer/Prototype-Producer.md](file:///d:/Git/Agents%20flow/Agents/Prototype-Producer/Prototype-Producer.md) / [.agents/skills/prototype-producer/SKILL.md](file:///d:/Git/Agents%20flow/.agents/skills/prototype-producer/SKILL.md)
- **Source archive:** [prototype-producer.zip](file:///d:/Git/Agents%20flow/prototype-producer.zip)
- **Memory path:** [Agent_Memory/Prototype-Producer/](file:///d:/Git/Agents%20flow/Agent_Memory/Prototype-Producer)
- **Inputs:** Game concept (`docs/concept/CONCEPT_DOCUMENT.md`), technical setup (`docs/setup/TECHNICAL_SPEC.md`), system GDDs, agent reports.
- **Outputs:** `docs/producer/REQUIREMENTS.md`, `docs/producer/TRACEABILITY.md`, `docs/producer/GDD_REVIEW.md`, `docs/producer/RECOMMENDATIONS.md`, `docs/producer/DEVELOPMENT_PLAN.md`.
- **Relationships:**
  - Upstream: User / Product Owner, Concepter-Agent (concept input), AF-Project-SetUp (tech stack)
  - Downstream: Game-Designer-Agent (system GDD tasks), Architect-Agent, Developer-Agent, Art/Audio agents
- **Handoff contract:** Receives approved concept and technical setup; delivers approved development plan, tracked agent assignments, and verifiable prototype milestones.
- **Status:** READY
- **Last validation:** 2026-10-14
- **Notes / blockers:** Fully installed and activated. Ready for prototype planning and agent orchestration via skill `/prototype-producer`.

### Asset-Artist
- **Name:** Asset-Artist
- **Version:** 0.3.0
- **Role:** 2D Game Asset Production, Style Testing, and Visual Pipeline Execution
- **Responsibilities:**
  - Read and analyze 4 inputs: Art Style Guide, GDD, Format Specifications, References.
  - Maintain input traceability and version tracking in `INPUT_REGISTRY.md`.
  - Compile production plans and select methods (T1 Code SVG/Canvas, T2 Image Tool, T3 Prompt Package).
  - Execute Style Test gate (2–3 assets + screen mockup) and obtain user approval prior to mass production.
  - Produce, post-process (trim, clean alpha, resize @1x/@2x/@3x), and organize assets in `Assets/`.
  - Validate assets against `QA_CHECKLIST.md` (technical and visual QA).
  - Maintain canonical registry `Assets/ASSET_MANIFEST.md` and export stable versions to `Assets/export/`.
  - Route missing data, blockers, and conflicts to input owners via `Agent_Memory/_Shared/REQUESTS/REQ-AA-####.md`.
- **Declared capabilities:** 2D art production, SVG/Canvas code rendering, AI prompt packaging, image post-processing, style testing, QA checklists.
- **Verified capabilities:** Filesystem read/write, markdown spec generation, Antigravity skill activation, directory structure management.
- **Required tools/dependencies:** Filesystem read/write for `Assets/` and `Agent_Memory/`, image viewing / generation tools when available.
- **Dependency status:** SATISFIED
- **Runtime:** Google Antigravity
- **Install path:** [Agents/Asset-Artist/Asset-Artist.md](file:///d:/Git/Agents%20flow/Agents/Asset-Artist/Asset-Artist.md) / [.agents/skills/asset-artist/SKILL.md](file:///d:/Git/Agents%20flow/.agents/skills/asset-artist/SKILL.md)
- **Source archive:** [asset-artist.zip](file:///d:/Git/Agents%20flow/asset-artist.zip)
- **Memory path:** [Agent_Memory/Asset-Artist/](file:///d:/Git/Agents%20flow/Agent_Memory/Asset-Artist)
- **Inputs:** Art Style Guide (`Inputs/Art_Style/` or `docs/art/`), GDD (`Inputs/GDD/`), Format Specs (`Inputs/Format_Specs/`), References (`Inputs/References/` or `docs/art/references/`), integration specs from Developer.
- **Outputs:** `Assets/ASSET_MANIFEST.md`, assets under `Assets/<category>/`, `Assets/export/`, `Assets/_src/`, `Assets/_style_tests/`, `Assets/_prompts/`.
- **Relationships:**
  - Upstream: User (approves style tests and final assets), Art-Style-Guide-Agent (art guide, format specs, refs), Game-Designer-Agent (GDD entities & states), Developer-Agent (engine & format integration)
  - Downstream: Developer-Agent (consumes exported assets from `Assets/export/`)
- **Handoff contract:** Receives task/GDD/art guide; delivers validated, versioned assets recorded in `Assets/ASSET_MANIFEST.md` with QA PASS or NOT_VERIFIED status.
- **Status:** READY
- **Last validation:** 2026-10-14
- **Notes / blockers:** Fully installed and activated. Ready for 2D asset generation and style testing via skill `/asset-artist`.

### Sound-Designer
- **Name:** Sound-Designer
- **Version:** 0.2.0
- **Role:** Game Audio Design, SFX Production, Musical Theme Direction, and Audio Mapping
- **Responsibilities:**
  - Request and verify 3 prerequisite inputs from Producer: Concept Document, GDD, Art Style Guide.
  - Halt and block work if any of the 3 prerequisite documents is missing.
  - Determine game audio direction, tone, and genre aesthetic based on concept and art style.
  - Clarify generation/sourcing tools with user and operate in `GENERATE`, `SOURCE`, or `PROMPT_ONLY` mode.
  - Formulate sound plan (actions, scenes, moods, durations, formats, licenses) and obtain user approval prior to mass production.
  - Produce, source, or specify prompts for SFX and musical themes in `Assets/Audio/{Sounds,Music,Prompts}`.
  - Maintain canonical audio map in `Assets/Audio/audio.md` linking actions to sounds and scenes to music.
  - Enforce strictly free/permissive licenses (CC0, CC-BY with attribution, commercial AI tool terms).
- **Declared capabilities:** SFX design, music direction, prompt engineering for audio, audio mapping, license verification.
- **Verified capabilities:** Filesystem read/write, markdown spec authoring, Antigravity skill activation, audio map structuring.
- **Required tools/dependencies:** Filesystem read/write for `Assets/Audio/` and `Agent_Memory/`, audio generation/sourcing tools as specified by user.
- **Dependency status:** SATISFIED
- **Runtime:** Google Antigravity
- **Install path:** [Agents/Sound-Designer/Sound-Designer.md](file:///d:/Git/Agents%20flow/Agents/Sound-Designer/Sound-Designer.md) / [.agents/skills/sound-designer/SKILL.md](file:///d:/Git/Agents%20flow/.agents/skills/sound-designer/SKILL.md)
- **Source archive:** [sound-designer.zip](file:///d:/Git/Agents%20flow/sound-designer.zip)
- **Memory path:** [Agent_Memory/Sound-Designer/](file:///d:/Git/Agents%20flow/Agent_Memory/Sound-Designer)
- **Inputs:** Concept Document (`docs/concept/CONCEPT_DOCUMENT.md`), GDD (`docs/gdd/`), Art Style Guide (`docs/art/` or `Inputs/Art_Style/`), user tool choices.
- **Outputs:** `Assets/Audio/audio.md`, SFX files in `Assets/Audio/Sounds/`, music files in `Assets/Audio/Music/`, prompt packages in `Assets/Audio/Prompts/`.
- **Relationships:**
  - Upstream: User (approves tool mode and audio plan), Prototype-Producer (provides 3 source documents)
  - Downstream: Developer-Agent (consumes audio files and `audio.md` for game integration)
- **Handoff contract:** Receives 3 source documents; delivers user-approved audio plan and populated `Assets/Audio/audio.md` with verified audio files or prompt packages.
- **Status:** READY
- **Last validation:** 2026-10-14
- **Notes / blockers:** Fully installed and activated. Ready for audio design, SFX planning, and music direction via skill `/sound-designer`.

### Build-n-QA
- **Name:** Build-n-QA
- **Version:** 1.0.0
- **Role:** Autonomous Unity Android Build, GDD Test Verification, Android UI QA, Developer Handoff, and Retesting
- **Responsibilities:**
  - Enforce strict read-only protection of source Unity project; execute builds exclusively in isolated staging copies (`staging/`).
  - Assemble Unity Android Development/Debug APKs integrating verified art assets from `Assets/export/`.
  - Ingest test scenarios from Game-Designer-Agent or derive measurable test cases with requirement traceability from GDD.
  - Autonomously drive compatibility-checked Android emulators via ADB / Android CLI, executing tap/swipe actions and collecting screenshots/logcat.
  - Package defect reports in markdown (`bug-report.md`) and schema-compliant JSON (`bugs.json`), dispatching handoffs to Developer-Agent.
  - Execute automated retest and dependency regression suites upon receiving developer fix revisions until 100% PASS is achieved.
  - Detect non-productive cycles (`STALLED` / `BLOCKED`) to prevent endless loops.
- **Declared capabilities:** Headless Unity Android builds, automated Android emulator UI control, GDD-to-test derivation, bug schema serialization, regression verification.
- **Verified capabilities:** Filesystem read/write, JSON schema validation, markdown spec generation, Antigravity skill activation, isolated staging directory layout.
- **Required tools/dependencies:** Unity Editor with Android Build Support, Android SDK / ADB (via `android-cli`), local Android emulator, access to `Agent_Memory/`.
- **Dependency status:** SATISFIED
- **Runtime:** Google Antigravity
- **Install path:** [Agents/Build-n-QA/Build-n-QA.md](file:///d:/Git/Agents%20flow/Agents/Build-n-QA/Build-n-QA.md) / [.agents/skills/build-n-qa/SKILL.md](file:///d:/Git/Agents%20flow/.agents/skills/build-n-qa/SKILL.md)
- **Source archive:** [build-n-QA_agent_package.zip](file:///d:/Git/Agents%20flow/build-n-QA_agent_package.zip)
- **Memory path:** [Agent_Memory/Build-n-QA/](file:///d:/Git/Agents%20flow/Agent_Memory/Build-n-QA)
- **Inputs:** Source Unity project (read-only), canonical GDD / test-cases from Game Designer, art assets from Asset Artist (`Assets/export/`), Developer fix commits.
- **Outputs:** `QA_Artifacts/Build-n-QA/<task_id>/<run_id>/` (Development `.apk`, `build-manifest.json`, `test-cases.json`, `test-results.json`, `qa-run-report.md`, `bugs.json`, `bug-report.md`, `developer-handoff.json`, `evidence/`).
- **Relationships:**
  - Upstream: Prototype-Producer (milestone triggers), Game-Designer-Agent (GDD & test cases), Asset-Artist (art assets)
  - Downstream: Developer-Agent (receives bug reports and handoffs; provides fix revisions)
- **Handoff contract:** Receives source project and test scope; delivers verified Development APK, executed test results with screenshot/log evidence, and defect handoff packages.
- **Status:** READY
- **Last validation:** 2026-10-14
- **Notes / blockers:** Fully installed and activated. Ready for autonomous Unity Android builds and emulator UI QA via skill `/build-n-qa`.









