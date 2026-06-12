# Mobile Feature Golden Path

Use this example when a ticket targets a Flutter, iOS, or Android mobile application.

## Example User Prompt

```text
Approval Status = APPROVED_FOR_DEVELOPMENT
Implement the approved mobile ticket for subscription reminder notifications.
```

## Route

- Stage: development
- Workflow: `workflows/backlog-to-development.md`
- Primary role: Flutter Developer, iOS Developer, Android Developer, or Mobile Lead
- Supporting roles: Product Designer, QA Developer, Automation Developer, Security Reviewer

## Required Inputs

- Approved ticket
- PRD reference
- Design or UX state reference
- Architecture notes
- Target platform: Flutter, iOS, Android, or mixed
- Notification, permissions, analytics, or backend dependency details

## Step 1: Select Platform Path

Flutter:

- Read `roles/flutter-developer.md`
- Read `skills/flutter-development/SKILL.md`
- Read `skills/flutter-development/stacks/riverpod.md` when Riverpod is detected

Native iOS:

- Read `roles/ios-developer.md`
- Read `skills/ios-development/SKILL.md`
- Read `skills/ios-development/stacks/swiftui.md` when SwiftUI is detected

Native Android:

- Read `roles/android-developer.md`
- Read `skills/android-development/SKILL.md`
- Read `skills/android-development/stacks/compose.md` when Compose is detected

## Step 2: Inspect Target Repository

Check:

- Repository `AGENTS.md`
- App architecture
- Feature/module structure
- Navigation pattern
- State management
- API/client layer
- Permission handling
- Existing tests
- Build and test commands

## Step 3: Define Implementation Slice

Break the feature into small slices:

- UI state and view changes
- Business logic or use case
- Data/repository changes
- Permission flow
- Analytics events
- Error and empty states
- Tests

Do not create unrelated app restructuring.

## Step 4: Implement Mobile Feature

Rules:

- Keep UI rendering separate from business logic.
- Keep platform permissions explicit and user-safe.
- Preserve accessibility labels where applicable.
- Follow existing navigation and state management patterns.
- Add analytics only when specified by PRD or architecture.
- Avoid storing sensitive data insecurely.

## Step 5: Test

Minimum verification by platform:

Flutter:

```bash
flutter analyze
flutter test
```

iOS:

```bash
xcodebuild test -scheme <Scheme> -destination 'platform=iOS Simulator,name=<Device>'
```

Android:

```bash
./gradlew test
./gradlew connectedAndroidTest
```

Use repository-specific commands when they differ.

## Step 6: QA Handoff

Include:

- Feature summary
- Platform and device coverage
- Permission flow notes
- Offline/error state behavior
- Test evidence
- Screenshots or recordings when UI changed
- Regression areas

## Expected Final Response Shape

```text
Mobile path: Flutter + Riverpod
Ticket: BEY-24
Implemented: reminder settings UI, notification permission state, reminder scheduler adapter
Verified: flutter analyze, flutter test
QA focus: permission denied state, reminder time edit, app restart persistence
Blockers: push notification backend endpoint is still mocked
```
