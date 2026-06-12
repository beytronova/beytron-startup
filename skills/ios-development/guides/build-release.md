# iOS Build and Release Guide

Use this guide when iOS work touches schemes, configurations, signing, provisioning, entitlements, capabilities, TestFlight, App Store release, privacy manifests, or CI/CD.

## Configuration Model

Common environments:

- `Debug`
- `Release`
- `Dev`
- `Staging`
- `Production`

Do not assume names. Follow repository convention first.

## Xcode Configuration Rules

- Keep environment-specific values out of source when they are secrets.
- Use schemes, configurations, xcconfig files, or repository-approved configuration.
- Keep bundle identifiers distinct by environment when required.
- Keep Firebase `GoogleService-Info.plist` aligned with bundle ID and environment.
- Do not commit signing credentials or secret values.

## Common Commands

Use repository commands first. Common commands:

```bash
xcodebuild -scheme App -configuration Debug -destination 'platform=iOS Simulator,name=iPhone 16' build
xcodebuild -scheme App -configuration Debug -destination 'platform=iOS Simulator,name=iPhone 16' test
xcodebuild -scheme App -configuration Release -archivePath build/App.xcarchive archive
swift test
pod install
```

## Signing and Provisioning Rules

- Store certificates, profiles, and signing secrets in approved CI or local secure storage.
- Do not paste signing secrets into docs, tickets, prompts, or logs.
- Keep entitlements reviewed before release.
- Do not add capabilities without approval.

## App Store and TestFlight Checks

- Bundle ID is correct.
- Version and build number are correct.
- Signing/provisioning is correct.
- Privacy manifest and required usage descriptions are reviewed.
- Export compliance and data collection declarations are known.
- Release notes are prepared.
- Rollback or phased rollout plan exists.

## Privacy Manifest and Usage Descriptions

Review when feature touches:

- Camera, photos, contacts, location, microphone, Bluetooth, health, financial data, tracking, analytics, push notifications, or device identifiers.

## Output Format

```text
iOS release config review: PASS|BLOCKED
Scheme/configuration: {value}
Bundle ID: {value}
Signing: {safe|blocked|unknown}
Privacy manifest: {reviewed|blocked|unknown}
Build commands: {list}
Release blockers: {list}
```

## Stop Conditions

Stop when:

- Environment or scheme is unclear.
- Signing credentials or secrets are requested in plaintext.
- Firebase config does not match bundle ID.
- Required privacy declaration is unknown.
- Release approval is missing for publishing.
