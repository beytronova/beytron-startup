---
name: flutter-development
description: Build approved Flutter work with Dart, feature-based architecture, Riverpod/BLoC/Provider, widget/business logic separation, platform integration, tests, and release checks.
---

# Flutter Development

Use this skill when approved work targets a Flutter app or shared mobile feature.

## Stack Guidance

- Dart and Flutter.
- Feature-based folder structure.
- Riverpod, BLoC, or Provider according to repo standard.
- Widgets for UI.
- Controllers/notifiers/blocs for state.
- Repositories/services for data access.
- Platform channels only when native behavior is required.

## Rules

- Do not put business logic in widgets.
- Keep feature boundaries explicit.
- Handle loading, empty, error, offline, and success states.
- Respect accessibility, localization, theming, and device form factors.
- Keep Firebase/native integrations behind abstractions.

## Verification

- `flutter analyze`.
- `flutter test`.
- Widget tests for UI states.
- Integration tests for critical flows when available.

## Outputs

- Flutter implementation plan.
- State management notes.
- Test evidence.
- Platform risk notes.
