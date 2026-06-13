---
name: ios-development
description: Build approved iOS work with Swift, SwiftUI/UIKit, MVVM, concurrency, XCTest, simulator validation, privacy, accessibility, and App Store readiness.
---

# iOS Development

Use this skill when approved work targets a native iOS app, iOS module, SwiftUI screen, UIKit flow, or Apple platform integration.

## Stack Guidance

- Swift.
- SwiftUI or UIKit according to repo architecture.
- MVVM or established local pattern.
- Async/await, Combine, or existing concurrency model.
- XCTest for unit and UI tests.

## Rules

- Keep view state separate from business logic.
- Keep platform permissions explicit.
- Respect accessibility labels, Dynamic Type, localization, and privacy manifests.
- Use Keychain for secrets where appropriate.
- Validate behavior on simulator or device when feasible.

## Verification

- Xcode build or repository build command.
- XCTest unit/UI tests.
- Simulator validation for UI flows.

## Outputs

- iOS implementation plan.
- Build/test evidence.
- Device or simulator notes.
- Release/privacy risk notes.
