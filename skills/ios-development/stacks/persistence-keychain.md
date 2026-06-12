# iOS Persistence and Keychain Deep Dive

Use this when iOS work touches local persistence, Core Data, SwiftData, UserDefaults, FileManager, cache behavior, Keychain, or secure storage.

## Stack Signals

- Code uses Core Data, SwiftData, `UserDefaults`, `FileManager`, SQLite wrappers, cache stores, Keychain wrappers, or security framework APIs.
- Feature stores user data, tokens, preferences, files, or offline cache.

## Primary Language

- Swift.

## Data Classification Rules

- Classify stored data before implementation.
- Treat tokens, auth data, financial data, health data, and precise location as sensitive.
- Do not store secrets in `UserDefaults`.
- Use Keychain or approved secure storage for tokens/secrets.

## Core Data and SwiftData Rules

- Keep persistence access behind repositories/services.
- Avoid persistence calls directly from Views/ViewControllers.
- Define migration behavior when schema changes.
- Keep model mapping explicit when domain models differ from persistence models.
- Avoid blocking the main thread with heavy fetches or writes.

## UserDefaults Rules

- Use for small non-sensitive preferences only.
- Keep keys centralized or documented according to repository convention.
- Avoid storing large data or sensitive values.

## File and Cache Rules

- Define cache invalidation and retention.
- Avoid unbounded local growth.
- Store files in appropriate app directories.
- Respect backup exclusion requirements when relevant.

## Keychain Rules

- Store tokens/secrets only when needed.
- Use access controls appropriate to the feature.
- Handle missing, expired, or inaccessible items.
- Do not log Keychain values.

## Testing

Common checks:

```bash
xcodebuild -scheme App -destination 'platform=iOS Simulator,name=iPhone 16' test
swift test
```

Recommended tests:

- Repository tests with in-memory/fake stores.
- Migration tests when supported.
- Keychain wrapper tests with safe test values.
- Cache invalidation tests.

## Do Not Do

- Do not store sensitive data in plaintext.
- Do not change schemas without migration notes.
- Do not access persistence directly from UI.
- Do not log stored sensitive values.

## Output Notes

When using this stack, report:

- Persistence model/schema impact
- Data classification
- Migration/cache behavior
- Keychain/secure storage impact
- Tests/checks run
