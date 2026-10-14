# QA Checklist

## Before Discovery exit
- [ ] Project structure and relevant documentation inspected.
- [ ] New versus existing project state understood.
- [ ] Target platforms and packaging requirements captured.
- [ ] Scene/rendering/input/performance requirements captured.
- [ ] Persistence/server/network/identity/analytics requirements captured as applicable.
- [ ] Budget, security/privacy and operational constraints considered.
- [ ] Contradictions and blockers recorded.
- [ ] User explicitly approved transition to Planning.

## Before Planning exit
- [ ] Stack fits requirements and actual project/runtime constraints.
- [ ] Alternatives and tradeoffs documented.
- [ ] Versions and compatibility assumptions identified.
- [ ] Security, data handling, licenses, costs and deployment targets considered.
- [ ] Technical spec and deployment plan agree with one another.
- [ ] Commands, prerequisites, validation and rollback are actionable.
- [ ] Risky/costly/irreversible actions have explicit approval gates.
- [ ] User explicitly approved both documents and transition to Deployment.

## Before and during Deployment
- [ ] Actual permissions/tools checked; no assumed capabilities.
- [ ] Disk space and runtime prerequisites checked.
- [ ] Existing work/repository status protected; backup/rollback considered.
- [ ] Secrets are not printed or written to reports.
- [ ] Public exposure, paid resources, destructive operations and privileged changes are gated.
- [ ] Material deviations stop execution and return to Planning.
- [ ] Each stage validated before continuing.
- [ ] Build/run/tests reported only if actually executed.

## Final report
- [ ] Changed artifacts and commands listed.
- [ ] PASS/FAIL/BLOCKED/NOT RUN states include evidence or reason.
- [ ] Run/stop instructions included where relevant.
- [ ] Known limitations and next steps listed.
- [ ] Memory and decision records updated or persistence limitation disclosed.
