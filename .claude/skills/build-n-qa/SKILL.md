---
name: build-n-qa
description: >-
  Autonomous Unity Android build, GDD test execution, emulator UI verification, bug handoff, and retest skill. Use this skill when building Unity Android development APKs in isolated staging, executing automated gameplay tests on Android emulators, reporting defects to Developer, or running regression suites.
---

# Build-n-QA Skill

This skill guides the agent through the autonomous Unity Android build, GDD-driven scenario testing, emulator UI verification, developer defect handoff, and regression retesting pipeline.

## Master Agent Specification & Manual
Full instructions, role boundaries, staging isolation rules, and schema contracts:
[Build-n-QA Master Spec](file:///d:/mydocs/GitHub/Agent-Flow/Agents/Build-n-QA/Build-n-QA.md)

---

## Standard Task Sequence

1. **Preflight & Discovery (Phase 0):**
   - Check personal memory: [MEMORY.md](file:///d:/mydocs/GitHub/Agent-Flow/Agent_Memory/Build-n-QA/MEMORY.md) and task history.
   - Inspect environment capabilities: Unity CLI, Android SDK / ADB, installed Android emulators.
   - Calculate source project fingerprint (git HEAD hash, dirty status).
   - Set up isolated staging (`staging/<task_id>/<run_id>/`) and artifacts directory (`QA_Artifacts/Build-n-QA/<task_id>/<run_id>/`).
2. **Isolated Unity Android Build (Phase 1):**
   - Clone source repository into staging.
   - Ingest approved assets from `Assets/export/`.
   - Execute headless Unity build to generate Development APK (`build.apk`).
   - Validate APK generation and produce `build-manifest.json`.
   - Re-verify immutability of the source repository.
3. **GDD Test Case Planning (Phase 2):**
   - Ingest test cases from Game-Designer-Agent or derive measurable test cases from canonical GDD.
   - Format test cases into `test-cases.json` ensuring end-to-end requirement traceability.
4. **Autonomous Emulator Testing & Visual QA (Phase 3):**
   - Launch compatible Android emulator via ADB / Android CLI.
   - Install build: `adb install -r build.apk`.
   - Execute test actions (taps, swipes, text input) and capture screenshots and logcat traces in `evidence/`.
   - Record observed results into `test-results.json` and generate `qa-run-report.md`.
5. **Defect Handoff (Phase 4):**
   - Deduplicate and document failures in `bugs.json` and `bug-report.md`.
   - Package `developer-handoff.json` and dispatch to Developer-Agent mailbox [Agent_Memory/_Mailbox/Developer/](file:///d:/mydocs/GitHub/Agent-Flow/Agent_Memory/_Mailbox/Developer).
6. **Retesting & Regression (Phases 5–6):**
   - Await developer fix revision.
   - Re-clone, rebuild APK in staging, and re-execute failed tests alongside dependency regression tests.
   - Iterate until 100% PASS is reached for all mandatory test cases.
7. **Documentation & Closure (Phase 7):**
   - Save task report in `Agent_Memory/Build-n-QA/tasks/`.
   - Update `WORK_LOG.md`, `DECISION_LOG.md`, and shared project state.
