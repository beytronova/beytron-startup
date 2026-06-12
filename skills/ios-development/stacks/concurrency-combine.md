# iOS Concurrency and Combine Deep Dive

Use this when iOS work touches async/await, Tasks, actors, MainActor, cancellation, Combine publishers, subscriptions, or reactive state.

## Stack Signals

- Code uses `async`, `await`, `Task`, `TaskGroup`, `actor`, `@MainActor`, `AnyPublisher`, `PassthroughSubject`, `CurrentValueSubject`, `sink`, or `AnyCancellable`.
- Architecture uses async services, Combine pipelines, or reactive view models.

## Primary Language

- Swift.

## Swift Concurrency Rules

- Keep UI updates on the main actor.
- Keep cancellation intentional and safe.
- Avoid unstructured tasks unless lifecycle is clear.
- Store and cancel tasks when owned by views/view models.
- Avoid blocking the main actor with heavy work.
- Use actors or serial execution where shared mutable state requires protection.

## Combine Rules

- Store cancellables with clear ownership.
- Avoid retain cycles in `sink` and closures.
- Map errors into domain/UI state.
- Avoid deeply nested publishers when simpler async/await works and repository convention permits it.
- Use schedulers intentionally.

## Error Handling

- Do not swallow errors silently.
- Convert technical errors into user-appropriate UI state.
- Treat cancellation separately from failures where relevant.

## Testing

Common checks:

```bash
xcodebuild -scheme App -destination 'platform=iOS Simulator,name=iPhone 16' test
swift test
```

Recommended patterns:

- Async XCTest with `async throws` tests.
- Dependency injection for async services.
- Test cancellation, success, error, loading, and retry behavior.
- Use test schedulers when repository uses them for Combine.

## Do Not Do

- Do not update UI off the main actor.
- Do not create runaway tasks from views.
- Do not retain `self` strongly in long-lived Combine subscriptions.
- Do not mix Combine and async/await without clear boundaries.

## Output Notes

When using this stack, report:

- Async/Combine flows changed
- MainActor boundaries
- Cancellation behavior
- Subscription ownership
- Tests/checks run
