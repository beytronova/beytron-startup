# iOS Development Skill

Use when implementing approved native iOS scope.

## Triggers

- Approved ticket targets a native iOS app.
- User asks for Swift, SwiftUI, UIKit, App Intents, permissions, networking, persistence, or iOS platform behavior.
- iOS release, privacy, accessibility, performance, or App Store impact must be evaluated.

## Supported Stacks

- Swift with SwiftUI
- Swift with UIKit when the repository is UIKit-first
- Combine, Observation, async/await, or existing reactive pattern
- Core Data, SwiftData, UserDefaults, FileManager, Keychain, or repository-defined persistence
- URLSession, GraphQL, or repository-defined networking stack
- Swift Package Manager or CocoaPods when already used
- XCTest, XCUITest, snapshot tests, and Swift Package tests
- dev/staging/production schemes and repository-defined build configurations

## Stack Deep Dives

After detecting the stack, read the matching deep dive when present:

- `skills/ios-development/stacks/swiftui.md`
- `skills/ios-development/stacks/uikit.md`
- `skills/ios-development/stacks/concurrency-combine.md`
- `skills/ios-development/stacks/persistence-keychain.md`
- `skills/ios-development/stacks/networking.md`
- `skills/ios-development/stacks/modular-di.md`

If the repository uses another architecture without a deep dive, follow repository conventions and this general skill.

## Guides

Read these guides when relevant:

- `skills/ios-development/guides/testing.md`
- `skills/ios-development/guides/performance.md`
- `skills/ios-development/guides/build-release.md`
- `skills/ios-development/guides/accessibility-i18n.md`
- `security/mobile-privacy.md`
- `security/secret-handling.md`
- `security/data-classification.md`

## Primary Languages

- Swift for app code
- Objective-C only in legacy repositories or approved bridging work
- YAML, xcconfig, plist, entitlement, or privacy manifest files for configuration when needed

## Project Structure Rules

- Follow the existing Xcode project and module layout.
- Prefer feature folders or modules when already present.
- Keep SwiftUI Views, UIKit Views, and ViewControllers focused on rendering, lifecycle, and interaction.
- Keep business logic in view models, models, services, use cases, or repositories.
- Keep networking, persistence, permissions, and Keychain access behind clear services.
- Keep dependency injection and protocol abstraction testable.
- Place tests in the existing unit/UI/package test targets.

## Architecture Patterns

- Prefer SwiftUI + MVVM, UIKit + MVVM/Coordinator, or the repository's established architecture.
- Use async/await for new asynchronous code unless the repo standard differs.
- Keep main-actor UI updates explicit.
- Use dependency injection or protocol abstraction for testable services.
- Keep app lifecycle, scene phase, background task, and permission flows explicit.
- Treat networking, persistence, Keychain, notifications, analytics, entitlements, and release configurations as architecture/privacy-relevant concerns.

## Coding Rules

- Respect Apple platform conventions and project design conventions.
- Implement only approved ticket scope.
- Handle permissions, privacy strings, Keychain, notifications, background modes, and App Groups intentionally.
- Avoid force unwraps unless impossible state is proven locally.
- Do not add entitlements, capabilities, dependencies, schemes, or signing changes without approval.
- Do not log secrets, tokens, push tokens, or sensitive user data.
- Keep user-facing strings compatible with repository localization patterns.

## Validation Commands

Use Xcode scheme/project commands from the repo first. Common commands:

```bash
xcodebuild -scheme App -destination 'platform=iOS Simulator,name=iPhone 16' build
xcodebuild -scheme App -destination 'platform=iOS Simulator,name=iPhone 16' test
xcodebuild -scheme App -configuration Release -archivePath build/App.xcarchive archive
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
- Relevant stack deep dives and guides listed above

## Protocol

1. Verify approval, PRD, architecture, design, ticket scope, and iOS targets.
2. Detect SwiftUI/UIKit usage, package manager, scheme, architecture, persistence, networking, privacy/capability impact, and test targets.
3. Read the matching stack deep dives and relevant guides.
4. Respect lifecycle, permissions, storage, networking, accessibility, privacy, performance, and App Store constraints.
5. Implement only approved scope.
6. Validate on simulator/device where possible.
7. Document tests, privacy implications, release impact, and QA handoff.

## Output Format

- Stack and architecture detected
- Stack deep dives and guides used
- Implementation summary
- Files changed
- iOS capability, permission, privacy, and release config impact
- Tests/checks run
- Simulator/device validation
- Performance/accessibility/i18n notes when relevant
- Risks and QA handoff

## Stop Conditions

- Approval is missing.
- Required entitlement/capability is unclear.
- Privacy behavior is undefined.
- Sensitive data, secrets, permissions, analytics, or tracking impact is unknown.
- Release scheme/signing/environment/privacy declaration is unclear for release-impacting work.
- Test target is unavailable and risk cannot be stated.

## Example Prompts

```text
Use iOS Development to implement this approved SwiftUI ticket and summarize validation, privacy, and release impact.
```
