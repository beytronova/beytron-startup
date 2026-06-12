# Flutter Firebase Stack Deep Dive

Use this when a Flutter repository integrates Firebase services.

## Stack Signals

- Dependencies such as `firebase_core`, `firebase_auth`, `cloud_firestore`, `firebase_messaging`, `firebase_crashlytics`, `firebase_analytics`, or `firebase_remote_config` exist.
- Platform files include `google-services.json` or `GoogleService-Info.plist`.
- Code calls Firebase SDK APIs.

## Primary Language

- Dart for Flutter code.
- Kotlin/Gradle and Swift/Xcode config only when platform configuration is approved.

## Firebase Service Rules

### Auth

- Keep auth state behind an auth repository/service.
- Do not expose tokens in logs, UI, issues, docs, or tests.
- Test signed-out, signed-in, expired session, and error states.

### Firestore/Realtime Database

- Keep database calls in repositories.
- Validate security rules expectations before relying on client-side checks.
- Avoid unbounded reads and large client-side scans.
- Model offline/cache behavior intentionally.

### FCM

- Treat push tokens as sensitive.
- Document notification permission flow.
- Handle foreground, background, terminated, denied, and token refresh states.

### Crashlytics

- Do not log secrets or sensitive personal data.
- Use non-sensitive breadcrumbs.
- Confirm crash collection behavior follows consent requirements where applicable.

### Analytics

- Do not send raw sensitive data as event properties.
- Use documented event names and property schema.
- Respect consent and opt-out rules.

### Remote Config

- Keep defaults in code.
- Handle fetch failure safely.
- Do not use remote config to bypass approvals or security gates.

## Platform Configuration Rules

- Android Firebase config must match package/application id and flavor.
- iOS Firebase config must match bundle id and flavor.
- Do not commit service account secrets.
- Treat downloaded config files as environment-specific and review repository policy.

## Testing

Common checks:

```bash
flutter analyze
flutter test
dart format .
```

Use emulator, fake repositories, or repository-approved Firebase test strategy when available.

## Do Not Do

- Do not call Firebase directly from widgets.
- Do not log tokens, user identifiers, or sensitive payloads.
- Do not add Firebase packages without architecture and privacy justification.
- Do not assume security rules are correct without review.

## Output Notes

When using Firebase, report:

- Firebase services touched
- Platform config impact
- Data/privacy impact
- Security rule assumptions
- Tests/checks run
- Manual verification needed
