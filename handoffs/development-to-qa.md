# Development to QA Handoff

## Purpose
Transfer completed implementation into validation with enough context for risk-based QA.

## Source Role
Implementing developer role

## Receiver Role
QA Developer

## Required Source Artifacts
- Jira issue or approved ticket scope
- PRD acceptance criteria
- Implementation summary
- Changed files or areas
- Tests run
- Tests skipped and why
- Known risks
- Environment or build notes

## Handoff Checklist
- [ ] Ticket link/key is included.
- [ ] Implementation summary is clear.
- [ ] Changed areas are listed.
- [ ] Acceptance criteria affected by the change are listed.
- [ ] Tests run are listed with results.
- [ ] Skipped tests are explained.
- [ ] Known risks and limitations are documented.
- [ ] Test environment is described.

## Receiver Outputs
- Test plan
- Test cases
- QA result
- Bug reports when needed
- Release readiness recommendation

## Acceptance Conditions
The handoff is accepted when QA can design and run validation without re-discovering what changed or why.

## Blocker Format
```text
Blocked because:
Needed from Developer:
QA impact if unresolved:
Recommended next step:
```

## Stop Conditions
- Implementation summary missing.
- Acceptance criteria missing.
- Test environment unavailable.
- Changed areas are unclear.
