# Flutter Riverpod Stack Deep Dive

Use this when a Flutter repository uses Riverpod for state management.

## Stack Signals
- `flutter_riverpod` or `riverpod` dependency exists.
- Code uses `Provider`, `StateProvider`, `NotifierProvider`, `AsyncNotifierProvider`, or generated providers.
- Widgets use `ConsumerWidget`, `ConsumerStatefulWidget`, or `ref.watch`.

## Primary Language
- Dart.

## File Structure Rules
- Keep providers feature-local unless genuinely shared.
- Keep business logic in Notifiers, services, use cases, or repositories.
- Keep widgets focused on rendering and user interaction.
- Keep models and DTOs separate when remote data shape differs from UI/domain shape.

## Architecture Rules
- Prefer `AsyncValue` for async loading/error/data state.
- Use repositories for remote/local data access.
- Use dependency injection through providers.
- Avoid calling APIs directly from widgets.
- Keep provider lifetimes intentional: `autoDispose` when appropriate.

## UI State Rules
- Handle `AsyncValue.loading`, `AsyncValue.error`, and data states.
- Keep error messages user-appropriate.
- Avoid rebuilding large widget trees unnecessarily.

## Testing
Common checks:

```bash
flutter analyze
flutter test
dart format .
```

For provider tests, use `ProviderContainer` and override dependencies.

## Do Not Do
- Do not put network or persistence calls directly in widgets.
- Do not create global providers for local screen state without reason.
- Do not ignore error/loading states.
- Do not overuse `ref.refresh` as a state management shortcut.

## Output Notes
When using this stack, report:

- Providers changed
- State flow
- Dependency overrides needed for tests
- UI states covered
- Tests/checks run
