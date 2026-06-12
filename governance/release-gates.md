# Release Gates

A release may proceed only when scope, QA evidence, rollback, risk, and monitoring are clear.

## Required Gates

- [ ] Release scope is clear.
- [ ] Included tickets are listed.
- [ ] QA status is known.
- [ ] Test evidence exists or skipped tests are explained.
- [ ] Critical blockers are resolved or explicitly accepted.
- [ ] Security/privacy review is complete when triggered.
- [ ] Migration or data risk is documented when relevant.
- [ ] Rollback plan exists.
- [ ] Release notes are prepared.
- [ ] Monitoring or follow-up plan exists.
- [ ] `APPROVED_FOR_RELEASE` is present.

## Go / No-Go Values

- Go: all gates pass.
- Conditional Go: minor accepted risks remain with owner and follow-up.
- No-Go: blocker, missing QA evidence, missing rollback, or missing approval.

## Blocker Conditions

- QA result is blocked or failed.
- Critical or high security risk is unresolved.
- Rollback path is missing for risky changes.
- Environment configuration is unknown.
- Required approval is missing.
- Monitoring is absent for high-impact release.

## Release Record Format

- Release owner
- Date
- Included tickets
- Commit/PR/release references
- QA status
- Known risks
- Rollback plan
- Monitoring plan
- Approval
- Follow-up items
