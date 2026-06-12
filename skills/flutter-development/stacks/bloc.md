# Flutter BLoC Stack Deep Dive

Use this when a Flutter repository uses BLoC or Cubit for state management.

## Stack Signals

- `flutter_bloc`, `bloc`, or `hydrated_bloc` dependency exists.
- Code uses `Bloc`, `Cubit`, `BlocProvider`, `BlocBuilder`, `BlocListener`, or `BlocConsumer`.
- Feature folders include `bloc/`, `cubit/`, `state`, or `event` files.

## Primary Language

- Dart.

## File Structure Rules

- Keep BLoC/Cubit feature-local unless shared state is intentional.
- Keep events and states explicit and easy to test.
- Keep UI widgets focused on rendering and dispatching user intent.
- Keep business logic in BLoC/Cubit, use cases, services, or repositories.
- Keep API/data models separate from UI state when complexity warrants it.

## Architecture Rules

- Prefer Cubit for simple state flows and BLoC for event-heavy flows.
- Use immutable states.
- Keep side effects in BLoC/Cubit or services, not directly in widgets.
- Use repositories for remote/local data access.
- Use dependency injection according to repository convention.
- Avoid emitting ambiguous state objects that make UI behavior hard to test.

## UI State Rules

- Cover loading, empty, error, success, permission, and offline states where relevant.
- Use `BlocListener` for one-time effects such as snackbars, navigation, and dialogs.
- Avoid starting network calls in `build` methods.
- Avoid rebuilding large trees unnecessarily; use `buildWhen` or selectors when needed.

## Testing

Common checks:

```bash
flutter analyze
flutter test
dart format .
```

Recommended package patterns:

- `bloc_test` for BLoC/Cubit behavior.
- `mocktail` or repository convention for mocks/fakes.
- Widget tests for UI state rendering.

## Do Not Do

- Do not put repository calls directly in widgets.
- Do not use BLoC as a global state dump.
- Do not mix unrelated feature state in one BLoC.
- Do not ignore error states.
- Do not emit states after close; guard async flows where needed.

## Output Notes

When using this stack, report:

- BLoC/Cubit files changed
- Events and states added or changed
- Repository dependencies
- UI states covered
- Tests/checks run
