# QA to Release Handoff

## Purpose
Transfer validated work into release preparation with explicit evidence, risks, and go/no-go recommendation.

## Source Role
QA Developer

## Receiver Role
DevOps Release

## Required Source Artifacts
- QA report
- Test evidence
- Included tickets
- Known issues
- Release scope
- Blockers and accepted risks
- Rollback risks
- Approval status

## Handoff Checklist
- [ ] QA result is explicit: pass, conditional pass, blocked, or fail.
- [ ] Test evidence is included or linked.
- [ ] Included tickets are listed.
- [ ] Known issues have severity.
- [ ] Critical blockers are resolved or explicitly accepted.
- [ ] Rollback risks are documented.
- [ ] Release approval state is included.

## Receiver Outputs
- Release checklist
- Release notes
- Rollback plan
- Monitoring plan
- Post-release follow-up

## Acceptance Conditions
The handoff is accepted when DevOps Release can decide release readiness using evidence rather than assumptions.

## Blocker Format
```text
Blocked because:
Needed from QA/Product/Developer:
Release impact if unresolved:
Recommended next step:
```

## Stop Conditions
- QA result is unclear.
- Critical blocker remains.
- Release approval missing.
- Rollback risk is unknown.
