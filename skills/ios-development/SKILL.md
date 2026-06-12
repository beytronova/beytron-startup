# iOS Development Skill

Use when implementing approved native iOS scope.

## Triggers
- Approved ticket targets a native iOS app.
- User asks for Swift, SwiftUI, UIKit, App Intents, permissions, or iOS platform behavior.
- iOS release or privacy impact must be evaluated.

## Supported Stacks
- Swift with SwiftUI
- Swift with UIKit when the repository is UIKit-first
- Combine, Observation, async/await, or existing reactive pattern
- Swift Package Manager or CocoaPods when already used
- XCTest and XCUITest

## Primary Languages
- Swift for app code
- Objective-C only in legacy repositories or approved bridging work
- YAML, xcconfig, plist, or entitlement files for configuration when needed

## Project Structure Rules
- Follow the existing Xcode project and module layout.
- Prefer feature folders or modules when already present.
- Keep views focused on rendering and interaction.
- Keep business logic in view models, models, services, use cases, or repositories.
- Keep networking, persistence, permissions, and Keychain access behind clear services.
- Place tests in the existing unit/UI test targets.

## Architecture Patterns
- Prefer SwiftUI + MVVM or the repository's established architecture.
- Use async/await for new asynchronous code unless the repo standard differs.
- Keep main-actor UI updates explicit.
- Use dependency injection or protocol abstraction for testable services.
- Keep app lifecycle, scene phase, background task, and permission flows explicit.

## Coding Rules
- Respect Apple platform conventions and project design conventions.
- Implement only approved ticket scope.
- Handle permissions, privacy strings, Keychain, notifications, background modes, and App Groups intentionally.
- Avoid force unwraps unless impossible state is proven locally.
- Do not add entitlements or capabilities without approval.

## Validation Commands
Use Xcode scheme/project commands from the repo first. Common commands:

```bash
xcodebuild -scheme App -destination 'platform=iOS Simulator,name=iPhone 16' build
xcodebuild -scheme App -destination 'platform=iOS Simulator,name=iPhone 16' test
swift test
pod install
```

## Required Reading
- Target repository `AGENTS.md`
- `roles/ios-developer.md`
- `roles/mobile-lead.md`
- `governance/coding-standards.md`
- `governance/testing-standards.md`
- `governance/security-standards.md`

## Protocol
1. Verify approval, PRD, architecture, design, ticket scope, and iOS targets.
2. Detect SwiftUI/UIKit usage, package manager, scheme, architecture, and test targets.
3. Respect lifecycle, permissions, storage, networking, accessibility, privacy, and App Store constraints.
4. Implement only approved scope.
5. Validate on simulator/device where possible.
6. Document tests, privacy implications, release impact, and QA handoff.

## Output Format
- Stack and architecture detected
- Implementation summary
- Files changed
- iOS capability or permission impact
- Tests/checks run
- Simulator/device validation
- Risks and QA handoff

## Stop Conditions
- Approval is missing.
- Required entitlement/capability is unclear.
- Privacy behavior is undefined.
- Test target is unavailable and risk cannot be stated.

## Example Prompts
```text
Use iOS Development to implement this approved SwiftUI ticket and summarize validation, privacy, and release impact.
```
