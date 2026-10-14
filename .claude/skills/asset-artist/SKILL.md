---
name: asset-artist
description: >-
  2D game asset production, style test verification, vector/code drawing (SVG/Canvas), and prompt packaging skill. Use this skill when creating, verifying, planning, or delivering game art assets, producing UI, tiles, backgrounds, character sprites, running style tests, validating against art style guides and GDDs, or generating asset manifests.
---

# Asset-Artist Skill

This skill guides the agent in producing, verifying, and delivering 2D game graphics for mobile/PC prototypes in strict compliance with the project's Art Style Guide, Game Design Document (GDD), and format specifications.

## Master Agent Specification & Manual
Full instructions, role boundaries, production methods, and QA contracts:
[Asset-Artist Master Spec](file:///d:/mydocs/GitHub/Agent-Flow/Agents/Asset-Artist/Asset-Artist.md)

---

## Standard Task Sequence

1. **Preflight & Tool Detection (Phase 0):**
   - Check personal memory: [MEMORY.md](file:///d:/mydocs/GitHub/Agent-Flow/Agent_Memory/Asset-Artist/MEMORY.md), open tasks, and answered requests `REQ-AA-*`.
   - Inspect active environment capabilities: image generation tools (T2), CLI graphics utilities (sharp/Pillow/cairosvg/ImageMagick), and image inspection capability.
2. **Discovery & Input Intake (Phase 1):**
   - Scan 4 core inputs (`Inputs/Art_Style/`, `Inputs/GDD/`, `Inputs/Format_Specs/`, `Inputs/References/` or corresponding `docs/art/` and `docs/gdd/` locations).
   - Update [INPUT_REGISTRY.md](file:///d:/mydocs/GitHub/Agent-Flow/Agent_Memory/Asset-Artist/INPUT_REGISTRY.md).
   - Classify missing parameters into `BLOCKER-ALL`, `BLOCKER`, or `NON-BLOCKING`.
3. **Requests & Conflicts (Phase 2):**
   - If blockers exist, author structured queries `REQ-AA-####.md` in [Agent_Memory/_Shared/REQUESTS/](file:///d:/mydocs/GitHub/Agent-Flow/Agent_Memory/_Shared/REQUESTS/).
   - Target queries to owners: Art Style Guide Agent (style, palette, refs), Game Designer Agent (GDD entities, states), Developer Agent (engine, integration formats).
4. **Production Planning (Phase 3):**
   - Compile asset list (`AS-####`, category, states, dimensions, densities, production method T1/T2/T3).
   - Register entries with status `PLANNED` or `BLOCKED`.
5. **Style Test & Screen Mockup (Phase 4 — Strict Gate):**
   - Produce 2–3 representative assets and a contextual screen mockup in `Assets/_style_tests/ST-###/`.
   - Submit `STYLE_TEST.md` to the user for explicit approval.
   - **Do not proceed to mass production without user approval.**
6. **Production & Post-processing (Phase 5):**
   - Execute production via T1 (Code: SVG/Canvas in `Assets/_src/`), T2 (Image Tool), or T3 (Prompt Package in `Assets/_prompts/`).
   - Post-process: clean alpha channel, trim/crop, verify padding, generate density scales (@1x, @2x).
7. **Quality Assurance (Phase 6):**
   - Validate each asset against [QA_CHECKLIST.md](file:///d:/mydocs/GitHub/Agent-Flow/Agents/Asset-Artist/QA_CHECKLIST.md).
8. **Delivery & Closure (Phases 7 & 8):**
   - Update canonical manifest [Assets/ASSET_MANIFEST.md](file:///d:/mydocs/GitHub/Agent-Flow/Assets/ASSET_MANIFEST.md).
   - Export approved assets to `Assets/export/`.
   - Document task report in `Agent_Memory/Asset-Artist/tasks/` and update `WORK_LOG.md`.
