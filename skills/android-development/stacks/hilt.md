# Android Hilt Dependency Injection Deep Dive

Use this when Android work touches Hilt, Dagger, dependency injection modules, qualifiers, scopes, or test replacement modules.

## Stack Signals

- Dependencies include Hilt or Dagger.
- Code uses `@HiltAndroidApp`, `@AndroidEntryPoint`, `@Inject`, `@Module`, `@Provides`, `@Binds`, qualifiers, or Hilt test annotations.

## Primary Language

- Kotlin.

## DI Rules

- Prefer constructor injection for classes you own.
- Use `@Binds` for interface-to-implementation bindings when possible.
- Use `@Provides` for third-party builders or complex construction.
- Keep scopes intentional.
- Use qualifiers when multiple bindings share a type.
- Keep modules organized by feature, data source, or repository convention.

## Android Entry Points

- Use `@AndroidEntryPoint` only where needed.
- Avoid injecting into objects with unclear lifecycle.
- Keep ViewModel injection consistent with repository pattern.

## Testing Rules

- Use fakes or test modules according to repository convention.
- Replace external services in tests.
- Do not use production credentials or services in tests.
- Keep dependency graph failures visible.

## Common Commands

```bash
./gradlew test
./gradlew connectedAndroidTest
./gradlew assembleDebug
./gradlew lint
```

## Do Not Do

- Do not introduce Hilt into a non-Hilt app without architecture approval.
- Do not create global mutable singleton state without justification.
- Do not use DI as a hidden service locator from UI code.
- Do not bind production implementations into test graphs.

## Output Notes

When using this stack, report:

- Modules/bindings changed
- Scopes and qualifiers
- Test replacement impact
- Dependency graph/build checks
