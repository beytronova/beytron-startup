# Android Development Stack Deep Dives

Use these files after `skills/android-development/SKILL.md` detects the target Android UI, architecture, persistence, networking, or dependency stack.

## Available Stacks

- `compose.md`: Kotlin Android applications using Jetpack Compose.
- `xml-views.md`: Android applications using XML layouts, Fragments, Activities, ViewBinding, DataBinding, RecyclerView, or Navigation Component.
- `coroutines-flow.md`: Android applications using Kotlin coroutines, Flow, StateFlow, SharedFlow, or lifecycle-aware collection.
- `room-datastore.md`: Android applications using Room, DataStore, local persistence, migrations, cache behavior, or encrypted storage.
- `networking.md`: Android applications using Retrofit, Ktor, OkHttp, GraphQL, API clients, interceptors, auth headers, or token refresh.
- `hilt.md`: Android applications using Hilt or Dagger dependency injection.

## Companion Guides

- `../guides/testing.md`
- `../guides/performance.md`
- `../guides/flavors-release.md`
- `../guides/accessibility-i18n.md`

## Selection Rule

Read the stack file that matches the target repository. If multiple stacks apply, read each relevant file.

Examples:

- Compose + Flow + Hilt: read `compose.md`, `coroutines-flow.md`, and `hilt.md`.
- XML Views + Retrofit + Room: read `xml-views.md`, `networking.md`, and `room-datastore.md`.
- Release variant work: read `../guides/flavors-release.md`.

If the repo uses another architecture without a dedicated stack file, follow repository conventions and the general Android skill.
