# Android Room and DataStore Deep Dive

Use this when Android work touches local persistence, Room, DataStore, cache behavior, migrations, or encrypted storage.

## Stack Signals

- Code uses `RoomDatabase`, `@Entity`, `@Dao`, SQL queries, migrations, `DataStore`, preferences, protobuf DataStore, or encrypted storage.
- Dependencies include Room, DataStore, SQLCipher, or AndroidX Security.

## Primary Language

- Kotlin.
- SQL where Room queries or migrations require it.

## Room Rules

- Keep database access behind repositories or data sources.
- Use DAOs for queries.
- Keep entity models separate from UI models when complexity warrants it.
- Add migrations for schema changes.
- Avoid destructive migrations unless explicitly approved.
- Use transactions for multi-step consistency requirements.
- Add indexes for frequently queried fields when needed.

## DataStore Rules

- Use DataStore for small key/value or typed preferences.
- Do not store large datasets in DataStore.
- Keep DataStore access behind a repository/service.
- Model default values and migration from SharedPreferences if needed.

## Security Rules

- Classify stored data.
- Use encrypted storage for tokens or sensitive values according to repository convention.
- Do not store secrets in plaintext.
- Avoid logging persisted sensitive values.

## Cache Rules

- Define source of truth.
- Define cache invalidation behavior.
- Handle offline reads and stale data explicitly.
- Avoid unbounded local growth.

## Testing

Common checks:

```bash
./gradlew test
./gradlew connectedAndroidTest
./gradlew lint
```

Recommended tests:

- DAO/query tests.
- Migration tests.
- Repository tests with fake/in-memory storage.
- DataStore default/migration tests.

## Do Not Do

- Do not change schema without migration plan.
- Do not access Room or DataStore directly from UI.
- Do not store sensitive values without classification and protection.
- Do not use local cache behavior that conflicts with product expectations.

## Output Notes

When using this stack, report:

- Entities/DAOs/migrations changed
- DataStore keys or schema changed
- Data classification
- Cache invalidation behavior
- Migration/testing evidence
