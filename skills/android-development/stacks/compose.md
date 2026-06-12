# Android Jetpack Compose Stack Deep Dive

Use this when a target Android repository uses Jetpack Compose.

## Stack Signals
- Compose dependencies exist.
- UI files use `@Composable`.
- Navigation may use Navigation Compose.

## Primary Language
- Kotlin.

## File Structure Rules
- Keep Composables focused on rendering and events.
- Keep state holders in ViewModels or dedicated state classes.
- Keep domain logic in use cases/services.
- Keep data access in repositories.
- Keep previews close to Composables when repository uses previews.

## Architecture Rules
- Prefer unidirectional data flow.
- Expose UI state from ViewModel using StateFlow, LiveData, or established pattern.
- Collect lifecycle-aware state in Composables.
- Keep side effects in `LaunchedEffect`, `DisposableEffect`, or ViewModel as appropriate.
- Use Navigation Compose according to repository convention.

## UI State Rules
- Model loading, empty, error, success, permission, and offline states.
- Keep accessibility semantics and content descriptions where needed.
- Avoid expensive work in Composables.

## Testing
Common checks:

```bash
./gradlew test
./gradlew connectedAndroidTest
./gradlew lint
./gradlew assembleDebug
```

Use Compose UI tests for critical interactions when existing repo supports them.

## Do Not Do
- Do not perform business logic directly inside Composables.
- Do not collect flows without lifecycle awareness when repo has lifecycle helpers.
- Do not create unstable state objects that trigger unnecessary recomposition.
- Do not add permissions or services without approval.

## Output Notes
When using this stack, report:

- Composables changed
- UI state model
- ViewModel/data flow impact
- Accessibility notes
- Tests/checks run
