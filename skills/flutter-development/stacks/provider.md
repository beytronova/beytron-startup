# Flutter Provider Stack Deep Dive

Use this when a Flutter repository uses Provider or ChangeNotifier for state management.

## Stack Signals

- `provider` dependency exists.
- Code uses `Provider`, `ChangeNotifierProvider`, `Consumer`, `Selector`, or `context.watch/read/select`.
- View models extend `ChangeNotifier`.

## Primary Language

- Dart.

## File Structure Rules

- Keep providers/view models feature-local unless shared state is intentional.
- Keep `ChangeNotifier` classes focused on one feature or bounded state concern.
- Keep widgets focused on rendering and user interaction.
- Keep business logic in view models, use cases, services, or repositories.
- Keep repository and API logic outside widgets.

## Architecture Rules

- Prefer explicit view model methods for user actions.
- Use repositories for data access.
- Keep `notifyListeners` usage intentional and minimal.
- Use `Selector` or `context.select` for granular rebuilds.
- Dispose controllers, subscriptions, and resources properly.

## UI State Rules

- Model loading, empty, error, success, permission, and offline states explicitly.
- Avoid calling async methods directly from `build`.
- Avoid using `Provider` as a hidden service locator for unrelated dependencies.

## Testing

Common checks:

```bash
flutter analyze
flutter test
dart format .
```

Recommended patterns:

- Unit test ChangeNotifier/view model behavior.
- Use fake repositories for state transitions.
- Widget test key UI states with provider overrides.

## Do Not Do

- Do not put network or persistence calls directly in widgets.
- Do not call `notifyListeners` excessively or inside tight loops.
- Do not store large unrelated state in one notifier.
- Do not ignore disposal of resources.

## Output Notes

When using this stack, report:

- Providers/view models changed
- State fields and transitions
- Rebuild controls used
- UI states covered
- Tests/checks run
