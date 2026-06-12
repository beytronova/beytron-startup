# Automation Testing Skill

Use when turning repeatable validation into automated checks.

## Triggers
- User asks to automate tests.
- QA identifies stable critical regression paths.
- CI needs repeatable validation for approved scope.

## Supported Tools
- Web: Playwright, Cypress, Jest, Vitest, Testing Library
- Backend/API: pytest, Jest/Vitest, Supertest, contract tests, Newman
- Flutter: flutter test, integration_test
- iOS: XCTest, XCUITest
- Android: JUnit, Robolectric, Espresso, Compose UI tests
- CI: GitHub Actions, GitLab CI, CircleCI, Bitrise, Fastlane, or repository-native automation

## Selector and Test Design Rules
- Prefer accessible selectors and user-visible behavior for UI tests.
- Use stable test IDs only when accessibility selectors are not enough.
- Avoid brittle selectors based on layout, generated class names, or timing.
- Make each failure actionable with clear assertion messages.
- Avoid sleeps; use explicit waits, polling, or framework-native synchronization.

## Test Data Rules
- Use deterministic fixtures, factories, seed scripts, or mocked services.
- Isolate tests from shared mutable state.
- Clean up created data where possible.
- Document required env vars, accounts, flags, and seed data.

## CI Rules
- Run fast checks early and expensive E2E checks later.
- Keep flaky tests quarantined or marked with owner and fix plan.
- Store artifacts such as screenshots, traces, videos, logs, and reports.
- Do not hide failures with broad retries; use retries only with flake tracking.

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
- Tool and layer selection
- Tests added or proposed
- Test data needs
- Selector strategy
- Flake risks
- Coverage gaps
- CI impact

## Stop Conditions
- Flow is unstable.
- Required test data is unavailable.
- Failure signal would be ambiguous.
- Automation would encode unresolved product decisions.

## Example Prompts
```text
Use Automation Testing to automate the stable high-risk checks from this QA plan and document CI impact, test data, and flake risks.
```
