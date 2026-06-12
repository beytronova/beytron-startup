# QA Checklist

Use this checklist before moving from QA to release.

## Required Inputs
- Ticket scope
- PRD acceptance criteria
- Implementation summary
- Changed areas
- Test environment
- Known risks
- Test evidence

## Checklist
- [ ] Acceptance criteria are mapped to tests.
- [ ] Happy paths are covered.
- [ ] Negative paths and edge cases are covered.
- [ ] Regression risk is assessed.
- [ ] Accessibility is assessed when UI exists.
- [ ] Platform/device/browser matrix is stated when relevant.
- [ ] Data, auth, permission, or privacy risks are tested when relevant.
- [ ] Automated checks are listed when available.
- [ ] Manual checks are listed when performed.
- [ ] Skipped or blocked tests are explained.
- [ ] Bugs/blockers include severity and reproduction notes.
- [ ] Release readiness recommendation is explicit.

## Pass Criteria
QA can move to release when evidence supports Ready or Conditional readiness and critical blockers are resolved or explicitly accepted.

## QA Recommendation Values
- Ready
- Conditional
- Blocked
- Not Ready

## Block Conditions
- Acceptance criteria are missing.
- Test environment is unavailable.
- Critical blocker is unresolved.
- Evidence is missing for critical paths.
- Release readiness is ambiguous.

## Missing Information Output
```text
QA is blocked because:
Missing evidence or blocker:
Release impact:
Owner to resolve:
Recommended next step:
```
