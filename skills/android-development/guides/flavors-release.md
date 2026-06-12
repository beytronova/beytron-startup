# Android Flavors and Release Guide

Use this guide when Android work touches build variants, product flavors, signing, Play release, ProGuard/R8, Firebase config, CI/CD, or release preparation.

## Environment Model

Common environments:

- `dev`
- `staging`
- `production`

Do not assume names. Follow repository convention first.

## Gradle Configuration Rules

- Keep environment-specific values out of source when they are secrets.
- Use product flavors, build types, BuildConfig fields, resources, or repository-approved config.
- Keep application IDs distinct by environment when required.
- Keep Firebase `google-services.json` aligned with application ID and flavor.
- Do not commit signing credentials or secret values.

## Common Commands

Use repository tasks first. Common commands:

```bash
./gradlew assembleDebug
./gradlew assembleRelease
./gradlew bundleRelease
./gradlew lint
./gradlew test
./gradlew connectedAndroidTest
```

Flavor examples:

```bash
./gradlew assembleDevDebug
./gradlew assembleStagingRelease
./gradlew bundleProductionRelease
```

## Signing Rules

- Store signing credentials in approved CI secrets or local secure storage.
- Do not paste keystore passwords into docs, tickets, prompts, or logs.
- Keep signing config reviewed before release.

## R8/ProGuard Rules

- Review keep rules when reflection, serialization, DI, or SDKs are involved.
- Test release/minified builds when changes could affect runtime behavior.
- Do not disable minification casually.

## Play Release Checks

- `versionCode` and `versionName` are correct.
- Application ID is correct.
- Signing is correct.
- Required privacy declarations are known.
- Release notes are prepared.
- Rollback or staged rollout plan exists.

## Firebase Config

- Config file matches application ID and environment.
- Analytics/Crashlytics behavior follows consent requirements where applicable.
- No service account secrets are committed.

## Output Format

```text
Android release config review: PASS|BLOCKED
Variant/flavor: {value}
Application ID: {value}
Signing: {safe|blocked|unknown}
Firebase config: {matched|blocked|unknown}
Build commands: {list}
Release blockers: {list}
```

## Stop Conditions

Stop when:

- Environment or variant is unclear.
- Signing credentials or secrets are requested in plaintext.
- Firebase config does not match application ID.
- Release approval is missing for publishing.
