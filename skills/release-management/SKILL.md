# Release Management Skill

Use when preparing approved, tested work for release.

## Triggers
- User asks for release plan, release notes, deployment, rollback, or monitoring.
- QA recommends release readiness.
- `APPROVED_FOR_RELEASE` is present.

## Required Reading
- `roles/devops-release.md`
- `workflows/qa-to-release.md`
- `handoffs/qa-to-release.md`
- `templates/RELEASE_PLAN.template.md`
- `governance/release-gates.md`

## Protocol
1. Confirm release approval and scope.
2. Review QA status, blockers, known risks, migrations, environment config, and dependencies.
3. Prepare release notes, deployment steps, rollback plan, and monitoring plan.
4. Stop if any release gate fails.
5. After release, record release outcome, incidents, and follow-up work.

## Output Format
- Release scope
- Included tickets
- QA status
- Known risks
- Deployment steps
- Rollback plan
- Monitoring plan
- Approval status

## Quality Gates
- QA evidence is clear.
- Rollback path exists.
- Critical risks are resolved or explicitly accepted.
- Monitoring/follow-up is defined.

## Stop Conditions
- Release approval is missing.
- QA status is unclear.
- Rollback plan is missing.
- Critical risk is unresolved.

## Example Prompts
```text
Use Release Management to prepare release notes, deployment checklist, rollback plan, and monitoring plan.
```
