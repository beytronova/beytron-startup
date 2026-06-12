# Android Development Skill

Use when implementing approved native Android scope.

## Triggers

- Approved ticket targets a native Android app.
- User asks for Kotlin/Java, Android lifecycle, permissions, storage, background work, networking, dependency injection, or Play release behavior.
- Android platform validation is needed.
- Android work touches performance, testing, release variants, accessibility, i18n, persistence, or privacy.

## Supported Stacks

- Kotlin-first Android projects
- Jetpack Compose or XML Views depending on repository standard
- ViewModel, StateFlow, LiveData, Coroutines, Flow, WorkManager, Room, DataStore, Retrofit, Ktor, Hilt, or repository-native stack
- Gradle with Android Gradle Plugin
- JUnit, Robolectric, Espresso, Compose UI testing, and instrumented tests
- dev/staging/production flavors and repository-defined build variants

## Stack Deep Dives

After detecting the stack, read the matching deep dive when present:

- `skills/android-development/stacks/compose.md`
- `skills/android-development/stacks/xml-views.md`
- `skills/android-development/stacks/coroutines-flow.md`
- `skills/android-development/stacks/room-datastore.md`
- `skills/android-development/stacks/networking.md`
- `skills/android-development/stacks/hilt.md`

If the repository uses another architecture without a deep dive, follow repository conventions and this general skill.

## Guides

Read these guides when relevant:

- `skills/android-development/guides/testing.md`
- `skills/android-development/guides/performance.md`
- `skills/android-development/guides/flavors-release.md`
- `skills/android-development/guides/accessibility-i18n.md`
- `security/mobile-privacy.md`
- `security/secret-handling.md`
- `security/data-classification.md`

## Primary Languages

- Kotlin for new Android code when possible
- Java only in Java-first legacy repositories or approved interop work
- XML for layouts/resources when the repo uses XML views
- Gradle Kotlin/Groovy DSL for build configuration

## Project Structure Rules

- Follow the existing Android module structure.
- Prefer feature/module organization when already present.
- Keep Composables or Views focused on rendering and interaction.
- Keep business logic in ViewModels, use cases, repositories, services, or domain modules.
- Keep persistence, network clients, permissions, and platform APIs behind clear abstractions.
- Keep dependency injection bindings scoped and testable.
- Place unit, UI, and instrumented tests in existing test source sets.

## Architecture Patterns

- Prefer MVVM or the repository's established architecture.
- Use Repository and UseCase patterns when data or domain logic is shared.
- Use Coroutines/Flow for async streams when already standard.
- Keep lifecycle-aware collection and cancellation explicit.
- Use WorkManager for deferrable background work when appropriate.
- Treat Room, DataStore, networking, push notifications, analytics, permissions, and release variants as architecture/privacy-relevant concerns.

## Coding Rules

- Respect Android platform conventions and project design conventions.
- Implement only approved ticket scope.
- Handle permissions, lifecycle, configuration changes, offline behavior, accessibility, and privacy intentionally.
- Avoid leaking Activities, Fragments, Views, Contexts, or long-running work.
- Do not add permissions, services, receivers, dependencies, or build variants without approval.
- Do not log secrets, tokens, push tokens, or sensitive user data.
- Keep user-facing strings compatible with repository localization patterns.

## Validation Commands

Use repository Gradle tasks first. Common commands:

```bash
./gradlew test
./gradlew connectedAndroidTest
./gradlew lint
./gradlew assembleDebug
./gradlew assembleRelease
./gradlew bundleRelease
./gradlew ktlintCheck
./gradlew detekt
```

## Required Reading

- Target repository `AGENTS.md`
- `roles/android-developer.md`
- `roles/mobile-lead.md`
- `governance/coding-standards.md`
- `governance/testing-standards.md`
- `governance/security-standards.md`
- Relevant stack deep dives and guides listed above

## Protocol

1. Verify approval, PRD, architecture, design, ticket scope, and Android API/device targets.
2. Detect Compose/XML, architecture, modules, package manager, DI, persistence, networking, build variants, and test setup.
3. Read the matching stack deep dives and relevant guides.
4. Respect lifecycle, permissions, storage, networking, accessibility, privacy, performance, and Play constraints.
5. Implement only approved scope.
6. Validate on emulator/device where possible.
7. Document tests, privacy implications, release impact, and QA handoff.

## Output Format

- Stack and architecture detected
- Stack deep dives and guides used
- Implementation summary
- Files changed
- Android capability, permission, privacy, and release config impact
- Tests/checks run
- Emulator/device validation
- Performance/accessibility/i18n notes when relevant
- Risks and QA handoff

## Stop Conditions

- Approval is missing.
- Required permission/capability is unclear.
- Privacy behavior is undefined.
- Sensitive data, secrets, permissions, or analytics impact is unknown.
- Release variant/signing/environment is unclear for release-impacting work.
- Test target is unavailable and risk cannot be stated.

## Example Prompts

```text
Use Android Development to implement this approved Kotlin/Compose ticket and summarize validation, privacy, and release impact.
```
