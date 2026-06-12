# QA Testing Skill

Use when validating approved development work and deciding whether it is ready for release.

## Triggers
- User asks for QA, test plan, validation, bug triage, or release readiness.
- Development work is complete or ready for QA.
- Acceptance criteria need test coverage.

## Required Reading
- `roles/qa-developer.md`
- `workflows/development-to-qa.md`
- `handoffs/development-to-qa.md`
- `templates/TEST_PLAN.template.md`
- `governance/testing-standards.md`
- `governance/definition-of-done.md`

## Protocol
1. Read ticket scope, acceptance criteria, implementation summary, changed areas, and known risks.
2. Map each acceptance criterion to test scenarios.
3. Cover happy path, negative path, edge cases, accessibility, regression, data, and platform risk.
4. Run available checks or document blockers.
5. Record evidence, defects, skipped tests, and release recommendation.
6. Escalate critical blockers instead of marking QA complete.

## Output Format
- QA scope
- Acceptance criteria mapping
- Test scenarios
- Evidence
- Bugs/blockers
- Skipped tests
- Release readiness recommendation

## Quality Gates
- Test coverage matches risk.
- Evidence is present or blockers are explicit.
- Critical defects block release.
- Recommendation is unambiguous.

## Stop Conditions
- Acceptance criteria are missing.
- Test environment is unavailable.
- Implementation summary is missing.
- Critical blocker is unresolved.

## Example Prompts
```text
Use QA Testing to validate this implementation and produce release readiness with evidence and blockers.
```
