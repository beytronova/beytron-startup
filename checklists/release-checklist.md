# Release Checklist

Use this checklist before executing or approving a release.

## Required Inputs
- Release scope
- Included tickets
- QA status and evidence
- Known risks
- Security/privacy review when triggered
- Migration/data risk when relevant
- Rollback plan
- Deployment target
- Monitoring plan
- Approval status

## Checklist
- [ ] Release scope is clear.
- [ ] Included tickets are listed.
- [ ] QA status is Ready or Conditional with accepted conditions.
- [ ] Test evidence exists or skipped tests are explained.
- [ ] Critical blockers are resolved or explicitly accepted.
- [ ] Security/privacy review is complete when triggered.
- [ ] Migration or data risk is documented when relevant.
- [ ] Environment and secret readiness are confirmed without exposing secret values.
- [ ] Rollback plan exists.
- [ ] Release notes are prepared.
- [ ] Monitoring or follow-up plan exists.
- [ ] Release owner is identified.
- [ ] `APPROVED_FOR_RELEASE` is present.

## Go / No-Go Values
- Go: all gates pass.
- Conditional Go: minor accepted risks remain with owner and follow-up.
- No-Go: blocker, missing QA evidence, missing rollback, or missing approval.

## Block Conditions
- QA result is blocked or failed.
- Critical or high security risk is unresolved.
- Rollback path is missing for risky changes.
- Environment configuration is unknown.
- Required approval is missing.
- Monitoring is absent for high-impact release.

## Missing Information Output
```text
Release is blocked because:
Missing gate:
Release impact:
Owner to resolve:
Recommended next step:
```
