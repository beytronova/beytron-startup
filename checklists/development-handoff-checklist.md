# Development Handoff Checklist

Use this checklist before moving completed implementation to QA.

## Required Inputs
- Ticket key or approved ticket scope
- Implementation summary
- Changed files or changed areas
- Tests run
- Tests skipped and reason
- Known risks
- Environment/build notes
- Release impact

## Checklist
- [ ] Ticket scope is referenced.
- [ ] Implementation summary explains what changed and why.
- [ ] Changed files or areas are listed.
- [ ] Acceptance criteria affected by the change are mapped.
- [ ] Tests/checks run are listed with results.
- [ ] Skipped tests are explained.
- [ ] Known risks and limitations are documented.
- [ ] Security/privacy impact is stated when relevant.
- [ ] Migration or release impact is stated when relevant.
- [ ] QA environment or build instructions are documented.
- [ ] Recommended QA focus areas are listed.

## Pass Criteria
Implementation can move to QA when QA can validate the change without rediscovering what changed, why it changed, or how to test it.

## Block Conditions
- Implementation summary is missing.
- Changed areas are unclear.
- Acceptance criteria are not mapped.
- Tests are skipped without explanation.
- QA cannot identify environment or build.

## Missing Information Output
```text
Development handoff is blocked because:
Missing handoff detail:
QA impact:
Owner to resolve:
Recommended next step:
```
