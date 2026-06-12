# Flutter Platform Channels Deep Dive

Use this when a Flutter feature requires native iOS or Android behavior through platform channels, federated plugins, MethodChannel, EventChannel, BasicMessageChannel, or FFI.

## Stack Signals

- Code uses `MethodChannel`, `EventChannel`, `BasicMessageChannel`, pigeon, FFI, or a federated plugin structure.
- Feature requires native SDKs, background execution, sensors, permissions, secure storage, widgets, notifications, or platform APIs not covered by existing packages.

## Primary Languages

- Dart for Flutter interface and platform abstraction.
- Swift for iOS implementation.
- Kotlin for Android implementation.

## Decision Rules

Before creating platform channel code:

1. Check whether a maintained package already exists.
2. Check repository architecture and native code conventions.
3. Confirm iOS and Android behavior requirements.
4. Confirm permission, privacy, and security impact.
5. Confirm testing strategy.

## Dart API Rules

- Hide channel calls behind a Dart service/repository interface.
- Keep channel method names stable and documented.
- Use typed request/response models where practical.
- Map platform errors into domain errors.
- Avoid invoking channels directly from widgets.

## Native Implementation Rules

- Keep native code minimal and scoped.
- Use main thread only when required by platform APIs.
- Handle lifecycle and cancellation.
- Avoid leaking activity/view controller references.
- Respect platform permission flows.
- Never log secrets, tokens, or sensitive native payloads.

## MethodChannel Rules

- Use for request/response native calls.
- Validate method arguments on both Dart and native sides.
- Return structured errors.

## EventChannel Rules

- Use for streams from native to Dart.
- Manage listener lifecycle.
- Stop native observers when Dart cancels subscription.

## Federated Plugin Rules

- Use when the capability may be reused across apps or needs clean per-platform packages.
- Keep platform interface package stable.
- Add platform implementation tests where possible.

## Testing

Common checks:

```bash
flutter analyze
flutter test
dart format .
```

Additional expected verification:

- Native build check for Android.
- Native build check for iOS.
- Manual device/simulator validation for platform behavior.
- Permission denied/granted flows.

## Do Not Do

- Do not add native code without architecture approval.
- Do not create platform-specific behavior that diverges silently.
- Do not bypass permission or privacy requirements.
- Do not expose platform exceptions directly to UI.

## Output Notes

When using platform channels, report:

- Channel type used
- Dart API added/changed
- iOS implementation impact
- Android implementation impact
- Permission/privacy impact
- Native validation performed or blocked
