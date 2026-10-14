# QA_CHECKLIST

## Preflight
- [ ] Correct project root established.
- [ ] Installer memory and shared registry read.
- [ ] ZIP inventory created; excluded paths respected.
- [ ] Runtime identified from evidence; relevant docs inspected.

## Security and integrity
- [ ] ZIP paths validated before extraction.
- [ ] No path traversal, absolute path escape, suspicious symlink or archive bomb.
- [ ] No archive-supplied script/binary/hook executed.
- [ ] Existing agents and memory preserved; conflicts handled explicitly.

## Installation
- [ ] Target path and format follow actual runtime docs.
- [ ] Required files and skill references are present.
- [ ] Missing memory defaults created without overwriting existing content.
- [ ] Registry entry contains role, paths, dependencies, relationships, and status.
- [ ] Capabilities and permissions distinguish declared from verified.

## Completion
- [ ] Every archive has a final status.
- [ ] Validation claims are evidence-based.
- [ ] Task report and installer memory updated.
- [ ] Blockers and next actions are explicit.
