# Android Testing Guide

Use this guide when adding or reviewing native Android tests.

## Test Types

### Unit Tests

Use for:

- ViewModels
- Use cases
- Repositories with fake dependencies
- Mappers and validators
- Coroutine/Flow behavior
- Business rules

### Robolectric Tests

Use for:

- Android framework behavior without device/emulator when repository supports it.
- Resource-dependent logic.
- ViewModel or UI-adjacent behavior requiring Android APIs.

### Instrumented Tests

Use for:

- Real device/emulator behavior.
- Permissions.
- Database behavior when local instrumentation is needed.
- End-to-end flows.

### Compose UI Tests

Use for:

- Compose screen states.
- User interactions.
- Navigation triggers.
- Accessibility semantics where practical.

### Espresso Tests

Use for:

- XML View flows.
- Fragment/Activity interactions.
- Legacy UI regression coverage.

## Tooling Patterns

Common tools:

- JUnit
- Truth/AssertJ
- MockK/Mockito
- kotlinx-coroutines-test
- Turbine for Flow testing
- Robolectric
- Espresso
- Compose UI testing
- Hilt testing utilities when DI is used

## Commands

Use repository Gradle tasks first. Common commands:

```bash
./gradlew test
./gradlew connectedAndroidTest
./gradlew lint
./gradlew assembleDebug
./gradlew ktlintCheck
./gradlew detekt
```

## Coroutine and Flow Tests

- Use `runTest`.
- Use test dispatchers.
- Avoid real delays.
- Test success, loading, error, cancellation, and retry behavior.
- Use Turbine or repository convention for Flow assertions.

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
Android test plan: {summary}
Tests added: {list}
Commands run: {list}
Device/emulator coverage: {list}
Coverage gaps: {list}
Manual validation needed: {list}
```

## Stop Conditions

Stop or report blocker when:

- Acceptance criteria cannot be tested.
- Required device behavior cannot be validated.
- Tests require unavailable credentials or external services.
- Existing test infrastructure is broken and blocks meaningful verification.
