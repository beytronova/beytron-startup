# iOS SwiftUI Stack Deep Dive

Use this when a target iOS repository uses SwiftUI.

## Stack Signals
- Views conform to `View`.
- App entry uses SwiftUI `App` protocol or SwiftUI view hierarchy.
- State uses `@State`, `@Binding`, `@ObservedObject`, `@StateObject`, `@Environment`, Observation, or Combine.

## Primary Language
- Swift.

## File Structure Rules
- Keep Views focused on rendering and interaction.
- Keep business logic in view models, models, services, use cases, or repositories.
- Keep networking, persistence, permissions, and Keychain access behind services.
- Keep reusable components in shared UI folders/modules.
- Keep previews near views when repository uses previews.

## Architecture Rules
- Prefer MVVM or repository-established architecture.
- Use Observation or ObservableObject according to project standard.
- Keep main actor UI updates explicit.
- Use async/await for new async flows unless repo uses Combine consistently.
- Use dependency injection/protocols for testable services.

## UI State Rules
- Model loading, empty, error, success, permission, and offline states.
- Use accessibility labels, hints, traits, and dynamic type where appropriate.
- Keep navigation consistent with repository pattern.

## Testing
Common checks:

```bash
xcodebuild -scheme App -destination 'platform=iOS Simulator,name=iPhone 16' build
xcodebuild -scheme App -destination 'platform=iOS Simulator,name=iPhone 16' test
swift test
```

## Do Not Do
- Do not put networking or persistence directly in Views.
- Do not use force unwraps for normal data flow.
- Do not update UI state off the main actor.
- Do not add entitlements or capabilities without approval.

## Output Notes
When using this stack, report:

- Views/view models changed
- State and navigation impact
- Permission/privacy impact
- Accessibility notes
- Tests/checks run
