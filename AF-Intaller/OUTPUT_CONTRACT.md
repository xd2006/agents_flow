# OUTPUT_CONTRACT

Each installation batch must produce:
1. An archive inventory.
2. Runtime detection note with evidence and documentation paths/URLs consulted.
3. One outcome per archive and reason.
4. List of installed/adapted files and target paths.
5. Memory directory and registry verification for each installed agent.
6. Declared vs verified capabilities, permissions, dependencies and relationships.
7. Validation results, unresolved blockers and next steps.
8. Task report saved under `Agent_Memory/AF-Intaller/tasks/` and updates to `WORK_LOG.md`/`MEMORY.md`.

Success is not merely extraction. `READY` requires runtime-compatible files, resolved required references, memory provision, registry entry and successful post-install checks. If files are copied to a portable location but runtime activation is unverified, use `INSTALLED` and clearly state activation is not verified.
