# POST_INSTALL_QA_SKILL

## Trigger
After every installation attempt.

## Checks
- Required files exist at the documented target paths.
- Skill references and relative links resolve.
- Runtime-specific layout matches inspected documentation.
- Memory directory and minimum files exist.
- Registry entry exists and relationships are internally consistent.
- Declared tool requirements are mapped to verified availability or marked missing.
- No unsafe archive code was executed.
- Activation status is evidence-based.

## Status rules
- `READY`: installed, required references resolved, memory and registry verified, required dependencies available, runtime readiness validated.
- `INSTALLED`: files copied/adapted and memory/registry verified, but activation or some runtime behavior not verified.
- `BLOCKED`: requires unresolved runtime, conflict, permission or dependency decision.
- `FAILED`: installation attempt failed; report partial changes.
- `SKIPPED_DUPLICATE`: same identity/version already installed.
