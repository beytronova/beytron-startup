# Flutter Development Skill

Use when implementing approved cross-platform mobile scope with Flutter.

## Triggers
- Approved ticket targets a Flutter app.
- User asks to implement Flutter UI, state, navigation, persistence, or integrations.
- Cross-platform mobile behavior needs validation.

## Supported Stacks
- Flutter stable with Dart
- Riverpod, BLoC, Provider, GetX, or the repository's existing state management
- go_router, Navigator 2.0, auto_route, or existing navigation pattern
- Firebase, REST, GraphQL, local database, or repository-defined integrations
- Federated plugins and platform channels when native capability is required

## Stack Deep Dives
After detecting the stack, read the matching deep dive when present:

- `skills/flutter-development/stacks/riverpod.md`

If the repository uses BLoC, Provider, GetX, or another state pattern without a deep dive, follow repository conventions and this general skill.

## Primary Languages
- Dart for Flutter application code
- Swift/Kotlin only for approved platform channel or plugin work
- YAML for Flutter configuration

## Project Structure Rules
- Follow the target repository structure first.
- Prefer feature-based organization such as `features/{feature}/presentation`, `domain`, and `data` when the repo supports it.
- Keep widgets focused on rendering and interaction.
- Keep business logic in controllers, notifiers, blocs, use cases, services, or repositories.
- Keep API/data models separate from UI models when complexity warrants it.
- Place widget, unit, and integration tests according to existing repository conventions.

## Architecture Patterns
- Keep state predictable and testable.
- Use repository pattern for persistence or remote data when shared.
- Use dependency injection if the repo already has it.
- Avoid platform-specific branching in UI unless behavior genuinely differs.
- Use platform channels only after checking existing packages and architecture constraints.

## Coding Rules
- Preserve existing state management and routing pattern.
- Implement only approved ticket scope.
- Handle loading, empty, error, offline, permission, and success states where relevant.
- Keep layout responsive across phone/tablet targets when required.
- Avoid blocking UI thread; use async patterns cleanly.
- Do not introduce new packages without justification.

## Validation Commands
Use repository commands first. Common commands:

```bash
flutter pub get
flutter analyze
flutter test
flutter test integration_test
flutter build apk
flutter build ios --no-codesign
dart format .
```

## Required Reading
- Target repository `AGENTS.md`
- `roles/flutter-developer.md`
- `roles/mobile-lead.md`
- `workflows/backlog-to-development.md`
- `governance/coding-standards.md`
- `governance/testing-standards.md`

## Protocol
1. Verify approval, PRD, architecture, design, ticket scope, and platform matrix.
2. Detect Flutter version, state management, routing, package manager, and test style.
3. Read the matching stack deep dive if available.
4. Keep business logic testable outside widgets.
5. Implement approved scope with platform differences, permissions, offline behavior, and performance in mind.
6. Run Flutter checks/tests where possible.
7. Document device/simulator validation, skipped checks, and QA handoff.

## Output Format
- Flutter version and state management detected
- Stack deep dive used when applicable
- Implementation summary
- Files changed
- State/navigation/data behavior
- Tests/checks run
- Device/simulator validation
- Risks and QA handoff

## Stop Conditions
- Approval is missing.
- Platform requirements are unclear.
- Native capability is required but undesigned.
- Test impact cannot be stated.

## Example Prompts
```text
Use Flutter Development to implement this approved mobile ticket using the repo's existing state management and produce platform validation notes.
```
