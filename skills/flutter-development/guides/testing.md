# Flutter Testing Guide

Use this guide when adding or reviewing Flutter tests.

## Test Types

### Unit Tests

Use for:

- Use cases
- Services
- Repositories with fake dependencies
- State managers such as Notifier, Cubit, BLoC, or ChangeNotifier
- Pure validation and formatting logic

### Widget Tests

Use for:

- UI states
- Forms
- Navigation triggers
- Error, empty, loading, permission, and success rendering
- Accessibility semantics where practical

### Integration Tests

Use for:

- End-to-end user flows
- Platform behavior
- Real navigation paths
- Permission flows
- Local persistence flows

### Golden Tests

Use when the repository already supports them or visual regression risk is high.

## Tooling Patterns

Common tools:

- `flutter_test`
- `integration_test`
- `bloc_test`
- `mocktail` or `mockito`
- repository-specific fake services

## Commands

Use repository commands first. Common commands:

```bash
flutter pub get
flutter analyze
flutter test
flutter test integration_test
dart format .
```

## Test Data Rules

- Prefer fakes over real network calls.
- Avoid real credentials.
- Avoid production Firebase or payment services.
- Keep fixtures small and readable.
- Cover timezone, locale, offline, empty, and error cases when relevant.

## State Management Testing

Riverpod:

- Use `ProviderContainer`.
- Override dependencies.
- Dispose containers.

BLoC:

- Use `bloc_test` for event/state sequences.
- Verify error and cancellation paths.

Provider:

- Unit test view models.
- Widget test provider overrides/fakes.

## Required Coverage by Feature

For approved feature work, cover at least:

- Happy path
- Error path
- Loading/empty path when relevant
- Permission denied path when relevant
- Regression risk areas from the ticket

## Output Format

```text
Flutter test plan: {summary}
Tests added: {list}
Commands run: {list}
Coverage gaps: {list}
Manual validation needed: {list}
```

## Stop Conditions

Stop or report blocker when:

- Acceptance criteria cannot be tested.
- Required platform behavior cannot be validated.
- Tests require unavailable credentials or external services.
- Existing test infrastructure is broken and blocks meaningful verification.
