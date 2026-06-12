# Testing Standards

## Core Rules

- Map tests to acceptance criteria and risk.
- Cover critical happy paths and failure modes.
- Include regression, accessibility, data, security, platform, and release risks when relevant.
- Report skipped or blocked tests.
- Use automation for repeatable high-value checks.
- Do not claim readiness without evidence.

## Test Layers

- Unit: deterministic logic and small components.
- Integration: API, persistence, service, or module boundaries.
- UI: critical user flows and state coverage.
- E2E: highest-value cross-system workflows.
- Manual: exploratory, visual, platform, permission, or release-sensitive checks.

## Evidence Requirements

Record command output, screenshots, logs, build links, environment, device/browser, test data, or explicit blocked reason.

## QA Recommendation Values

- Ready
- Conditional
- Blocked
- Not Ready

## Stop Conditions

- Acceptance criteria are missing.
- Test environment is unavailable.
- Critical risk has no test or mitigation.
- Failed tests are not understood.
