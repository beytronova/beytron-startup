# Android Development Skill

Use when implementing approved native Android scope.

## Triggers
- Approved ticket targets a native Android app.
- User asks for Kotlin/Java, Android lifecycle, permissions, storage, background work, or Play release behavior.
- Android platform validation is needed.

## Supported Stacks
- Kotlin-first Android projects
- Jetpack Compose or XML Views depending on repository standard
- ViewModel, StateFlow, LiveData, Coroutines, WorkManager, Room, DataStore, Retrofit, Ktor, or repository-native stack
- Gradle with Android Gradle Plugin
- JUnit, Robolectric, Espresso, Compose UI testing, and instrumented tests

## Stack Deep Dives
After detecting the stack, read the matching deep dive when present:

- `skills/android-development/stacks/compose.md`

If the repository uses XML Views or another architecture without a deep dive, follow repository conventions and this general skill.

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
- Place unit, UI, and instrumented tests in existing test source sets.

## Architecture Patterns
- Prefer MVVM or the repository's established architecture.
- Use Repository and UseCase patterns when data or domain logic is shared.
- Use Coroutines/Flow for async streams when already standard.
- Keep lifecycle-aware collection and cancellation explicit.
- Use WorkManager for deferrable background work when appropriate.

## Coding Rules
- Respect Android platform conventions and project design conventions.
- Implement only approved ticket scope.
- Handle permissions, lifecycle, configuration changes, offline behavior, accessibility, and privacy intentionally.
- Avoid leaking Activities, Contexts, or long-running work.
- Do not add permissions, services, receivers, or dependencies without approval.

## Validation Commands
Use repository Gradle tasks first. Common commands:

```bash
./gradlew test
./gradlew connectedAndroidTest
./gradlew lint
./gradlew assembleDebug
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

## Protocol
1. Verify approval, PRD, architecture, design, ticket scope, and Android API/device targets.
2. Detect Compose/XML, architecture, modules, package manager, and test setup.
3. Read the matching stack deep dive if available.
4. Respect lifecycle, permissions, storage, networking, accessibility, privacy, and Play constraints.
5. Implement only approved scope.
6. Validate on emulator/device where possible.
7. Document tests, privacy implications, release impact, and QA handoff.

## Output Format
- Stack and architecture detected
- Stack deep dive used when applicable
- Implementation summary
- Files changed
- Android capability or permission impact
- Tests/checks run
- Emulator/device validation
- Risks and QA handoff

## Stop Conditions
- Approval is missing.
- Required permission/capability is unclear.
- Privacy behavior is undefined.
- Test target is unavailable and risk cannot be stated.

## Example Prompts
```text
Use Android Development to implement this approved Kotlin/Compose ticket and summarize validation, privacy, and release impact.
```
