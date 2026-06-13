---
name: android-development
description: Build approved Android work with Kotlin, Jetpack Compose/XML, ViewModel, Repository, UseCase, coroutines, Gradle, tests, privacy, and Play readiness.
---

# Android Development

Use this skill when approved work targets a native Android app, Android module, Compose screen, XML view, or platform integration.

## Stack Guidance

- Kotlin.
- Jetpack Compose or XML according to repo architecture.
- ViewModel, Repository, and UseCase boundaries.
- Coroutines and Flow for async/reactive work.
- Hilt or existing DI pattern.
- Room/DataStore when local persistence is required.

## Rules

- Keep UI state separate from domain logic.
- Keep permissions explicit and minimal.
- Respect accessibility, localization, adaptive layouts, and privacy requirements.
- Keep network/data code behind repositories.
- Avoid platform-specific hacks without documenting risk.

## Verification

- Gradle build/test commands.
- Unit tests for use cases and ViewModels.
- UI tests for critical flows when available.
- Emulator/device validation when feasible.

## Outputs

- Android implementation plan.
- Build/test evidence.
- Device matrix notes.
- Release/privacy risk notes.
