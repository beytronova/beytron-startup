# iOS Development Stack Deep Dives

Use these files after `skills/ios-development/SKILL.md` detects the target iOS UI, architecture, persistence, networking, concurrency, or dependency stack.

## Available Stacks

- `swiftui.md`: Native iOS applications using SwiftUI.
- `uikit.md`: iOS applications using UIKit, ViewControllers, Storyboards, XIBs, table views, collection views, or coordinators.
- `concurrency-combine.md`: iOS applications using async/await, Tasks, actors, MainActor, Combine, subscriptions, or reactive state.
- `persistence-keychain.md`: iOS applications using Core Data, SwiftData, UserDefaults, FileManager, cache stores, Keychain, or secure storage.
- `networking.md`: iOS applications using URLSession, API clients, GraphQL, auth headers, token refresh, retries, decoding, or offline cache.
- `modular-di.md`: iOS applications using Swift Package modules, frameworks, service containers, protocol abstraction, or dependency injection.

## Companion Guides

- `../guides/testing.md`
- `../guides/performance.md`
- `../guides/build-release.md`
- `../guides/accessibility-i18n.md`

## Selection Rule

Read the stack file that matches the target repository. If multiple stacks apply, read each relevant file.

Examples:

- SwiftUI + async/await + URLSession: read `swiftui.md`, `concurrency-combine.md`, and `networking.md`.
- UIKit + Core Data + Coordinator: read `uikit.md`, `persistence-keychain.md`, and `modular-di.md`.
- Release/signing work: read `../guides/build-release.md`.

If the repo uses another architecture without a dedicated stack file, follow repository conventions and the general iOS skill.
