# Android Coroutines and Flow Deep Dive

Use this when Android work touches Kotlin coroutines, Flow, StateFlow, SharedFlow, suspend functions, structured concurrency, or lifecycle-aware collection.

## Stack Signals

- Code uses `suspend`, `CoroutineScope`, `viewModelScope`, `lifecycleScope`, `Flow`, `StateFlow`, `SharedFlow`, `collect`, or `collectAsStateWithLifecycle`.
- Dependencies include Kotlin coroutines or lifecycle runtime KTX.

## Primary Language

- Kotlin.

## Architecture Rules

- Use structured concurrency.
- Prefer `viewModelScope` for ViewModel-owned work.
- Use repository/use case layers for async data operations.
- Keep dispatcher choices explicit for IO or CPU-heavy work.
- Keep cancellation safe and expected.
- Avoid launching untracked global work.

## Flow Rules

- Use `StateFlow` for observable UI state.
- Use `SharedFlow` or channels for one-time events only when repository convention supports it.
- Collect with lifecycle awareness in UI.
- Avoid collecting flows in a way that leaks lifecycle owners.
- Map errors into domain/UI state instead of crashing collectors.

## Dispatcher Rules

- Use IO dispatcher for blocking disk/network work.
- Avoid heavy work on Main.
- Inject dispatchers when tests need deterministic control.
- Do not hardcode dispatchers if repository has dispatcher providers.

## Error Handling

- Handle cancellation separately from failures where needed.
- Do not swallow exceptions silently.
- Surface user-appropriate errors through UI state.
- Keep retry behavior explicit and bounded.

## Testing

Common checks:

```bash
./gradlew test
./gradlew lint
```

Recommended patterns:

- Use `kotlinx-coroutines-test`.
- Use `runTest`.
- Use test dispatchers.
- Test success, error, cancellation, and loading states.

## Do Not Do

- Do not use `GlobalScope`.
- Do not block with `runBlocking` in production paths.
- Do not collect indefinitely outside lifecycle-aware scopes.
- Do not update UI state from background threads unsafely.

## Output Notes

When using this stack, report:

- Coroutine scopes changed
- Flow/StateFlow changes
- Dispatcher/test dispatcher impact
- Cancellation/error handling
- Tests/checks run
