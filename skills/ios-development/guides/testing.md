# iOS Testing Guide

Use this guide when adding or reviewing iOS tests.

## Test Types

### Unit Tests

Use for:

- View models
- Use cases
- Services
- Repositories with fake dependencies
- Mappers and validators
- Async/Combine behavior
- Business rules

### UI Tests

Use for:

- Critical user flows
- Navigation
- Forms
- Permission flows
- Regression-prone screens

### Snapshot Tests

Use when repository already supports them or visual regression risk is high.

### Package Tests

Use `swift test` for Swift Package targets when available.

## Tooling Patterns

Common tools:

- XCTest
- XCUITest
- Swift Testing when repository uses it
- Snapshot testing libraries when already present
- Mock URLProtocol or repository networking test helpers
- Test schedulers for Combine when repository uses them

## Commands

Use repository commands first. Common commands:

```bash
xcodebuild -scheme App -destination 'platform=iOS Simulator,name=iPhone 16' build
xcodebuild -scheme App -destination 'platform=iOS Simulator,name=iPhone 16' test
swift test
```

## Async Tests

- Use async XCTest when supported.
- Test success, loading, error, cancellation, and retry behavior.
- Avoid arbitrary sleeps.
- Inject clocks/schedulers/services when repository supports it.

## UI Test Rules

- Use stable accessibility identifiers for test-critical controls.
- Avoid relying on text that may be localized unless intentional.
- Keep UI tests focused on critical flows.
- Reset app state between tests according to repository convention.

## Test Data Rules

- Prefer fakes over real network calls.
- Do not use production credentials.
- Avoid production Firebase/payment services.
- Keep fixtures minimal and readable.
- Cover timezone, locale, offline, empty, and error cases when relevant.

## Required Coverage by Feature

For approved feature work, cover at least:

- Happy path
- Error path
- Loading/empty path when relevant
- Permission denied path when relevant
- Regression risk areas from the ticket

## Output Format

```text
iOS test plan: {summary}
Tests added: {list}
Commands run: {list}
Simulator/device coverage: {list}
Coverage gaps: {list}
Manual validation needed: {list}
```

## Stop Conditions

Stop or report blocker when:

- Acceptance criteria cannot be tested.
- Required device behavior cannot be validated.
- Tests require unavailable credentials or external services.
- Existing test infrastructure is broken and blocks meaningful verification.
