# Automation Testing Skill

Use when turning repeatable validation into automated checks.

## Triggers
- User asks to automate tests.
- QA identifies stable critical regression paths.
- CI needs repeatable validation for approved scope.

## Required Reading
- `roles/automation-developer.md`
- `roles/qa-developer.md`
- `templates/TEST_PLAN.template.md`
- `governance/testing-standards.md`

## Protocol
1. Identify high-value, stable, repeatable scenarios from the test plan.
2. Select the right test layer: unit, integration, API, UI, E2E, or CI workflow.
3. Define test data, environment, setup, teardown, and failure signal.
4. Implement deterministic checks using existing project patterns.
5. Document coverage gaps, flake risks, and maintenance expectations.
6. Hand results back to QA and release.

## Output Format
- Automation scope
- Test layer selection
- Tests added or proposed
- Test data needs
- Flake risks
- Coverage gaps
- CI impact

## Quality Gates
- Automated tests are deterministic.
- Failures are actionable.
- Test value exceeds maintenance cost.
- Coverage maps to risk.

## Stop Conditions
- Flow is unstable.
- Required test data is unavailable.
- Failure signal would be ambiguous.
- Automation would encode unresolved product decisions.

## Example Prompts
```text
Use Automation Testing to automate the stable high-risk checks from this QA plan and document CI impact.
```
