# Mobile Privacy

Use this guide for Flutter, iOS, and Android features that access device data, permissions, notifications, location, contacts, photos, health, biometrics, financial data, or analytics identifiers.

## Permission Rules

- Request permissions only at the moment of need.
- Explain the user value before permission prompts when appropriate.
- Provide a fallback path when permission is denied.
- Do not repeatedly prompt after denial.
- Keep permission handling testable.

## Sensitive Mobile Data

Treat the following as sensitive:

- Location
- Contacts
- Photos and media
- Health data
- Financial data
- Device identifiers
- Biometrics
- Push notification tokens
- Authentication tokens

## Platform Review

For iOS:

- Confirm required `Info.plist` usage descriptions.
- Confirm privacy declarations when applicable.
- Confirm Keychain use for secrets/tokens.

For Android:

- Confirm manifest permissions.
- Confirm runtime permission handling.
- Confirm encrypted storage for sensitive tokens.

For Flutter:

- Confirm platform-specific permission configuration.
- Confirm plugin privacy implications.
- Confirm secure storage usage when storing tokens.

## Analytics Rules

- Do not send raw sensitive data as event properties.
- Use coarse, non-identifying values where possible.
- Document event names and property schema.
- Respect consent and opt-out requirements.

## Output Format

```text
Mobile privacy review: PASS|BLOCKED
Permissions: {list}
Sensitive data: {list}
Storage: {safe|unsafe|unknown}
Analytics: {safe|unsafe|unknown}
Blockers: {list}
```
