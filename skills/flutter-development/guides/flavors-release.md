# Flutter Flavors and Release Guide

Use this guide when Flutter work touches build variants, environments, signing, app identifiers, Firebase config, CI/CD, or release preparation.

## Environment Model

Common environments:

- `dev`
- `staging`
- `production`

Do not assume environment names. Follow repository convention first.

## Configuration Rules

- Keep environment-specific values out of source when they are secrets.
- Use `--dart-define`, generated config, flavors, or existing repository pattern.
- Do not hardcode API keys, tokens, or credentials.
- Keep bundle identifiers/application IDs distinct by environment when required.
- Keep Firebase config aligned with environment and platform identifiers.

## Flutter Build Commands

Common commands:

```bash
flutter build apk --flavor <flavor> --dart-define=ENV=<env>
flutter build appbundle --flavor <flavor> --dart-define=ENV=<env>
flutter build ios --flavor <flavor> --dart-define=ENV=<env> --no-codesign
```

Use repository-specific scripts first.

## Android Release Checks

- Application ID and flavor are correct.
- Signing config is not committed with secrets.
- ProGuard/R8 rules are reviewed when enabled.
- Version code/name are correct.
- Firebase `google-services.json` matches the variant.

## iOS Release Checks

- Bundle ID and scheme are correct.
- Signing team/profile is handled by approved CI or local setup.
- `GoogleService-Info.plist` matches the variant.
- Version/build number are correct.
- Privacy usage descriptions are present.

## CI/CD Rules

- Use CI secrets for signing and credentials.
- Do not print secrets in logs.
- Keep build artifacts traceable to commit and ticket.
- Release publishing requires `Approval Status = APPROVED_FOR_RELEASE`.

## Output Format

```text
Flutter release config review: PASS|BLOCKED
Environment/flavor: {value}
Android impact: {summary}
iOS impact: {summary}
Secrets/signing: {safe|blocked|unknown}
Build commands: {list}
Release blockers: {list}
```

## Stop Conditions

Stop when:

- Environment is unclear.
- Signing credentials or secrets are requested in plaintext.
- Firebase config does not match bundle/application ID.
- Release approval is missing for publishing.
