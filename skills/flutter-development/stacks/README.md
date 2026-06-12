# Flutter Development Stack Deep Dives

Use these files after `skills/flutter-development/SKILL.md` detects the target Flutter architecture, state management, or integration stack.

## Available Stacks

- `riverpod.md`: Flutter applications using Riverpod providers and `AsyncValue` patterns.
- `bloc.md`: Flutter applications using BLoC or Cubit.
- `provider.md`: Flutter applications using Provider or ChangeNotifier.
- `firebase.md`: Flutter applications using Firebase Auth, Firestore, FCM, Crashlytics, Analytics, or Remote Config.
- `platform-channels.md`: Flutter applications using MethodChannel, EventChannel, BasicMessageChannel, federated plugins, or native platform integrations.

## Companion Guides

- `../guides/performance.md`
- `../guides/testing.md`
- `../guides/flavors-release.md`
- `../guides/accessibility-i18n.md`

## Selection Rule

Read the stack file that matches the target repository. If multiple stacks apply, read each relevant file.

Examples:

- Riverpod + Firebase: read `riverpod.md` and `firebase.md`.
- BLoC + platform channel: read `bloc.md` and `platform-channels.md`.
- Provider + release flavor work: read `provider.md` and `../guides/flavors-release.md`.

If the repo uses GetX or another pattern without a dedicated stack file, follow the repository convention and the general Flutter skill.
