# AGENT_INSTALLATION_SKILL

## Trigger
After runtime and archive validation pass.

## Procedure
1. Determine stable agent ID/name/version from manifest/spec; normalize directory name without changing declared identity.
2. Map portable prompt and skill files to target runtime conventions using inspected docs.
3. Keep a copy of the source package or its archive reference; distinguish generated runtime adapters from source files.
4. Compare with installed agent. Same identity/version: `SKIPPED_DUPLICATE`. Conflict: preserve current files, create a safe backup/side-by-side version only if supported; otherwise `BLOCKED_CONFLICT`.
5. Install from staging only after validation. Do not run archive scripts, package installers, hooks or generated code.
6. Do not claim runtime activation until documented activation/reload checks are performed.

## Failure handling
Leave source archive untouched, clean only the installer's own temporary staging files when safe, record partial changes, and mark `FAILED` or `BLOCKED`.
