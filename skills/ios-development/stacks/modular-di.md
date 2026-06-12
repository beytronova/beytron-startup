# iOS Modular Architecture and Dependency Injection Deep Dive

Use this when iOS work touches module boundaries, Swift Package Manager modules, CocoaPods modules, service containers, protocol abstraction, dependency injection, or test doubles.

## Stack Signals

- Repository has multiple Xcode targets, Swift packages, frameworks, feature modules, or shared modules.
- Code uses protocol-based services, dependency containers, coordinators, factories, or environment objects.

## Primary Language

- Swift.

## Modular Architecture Rules

- Respect existing module boundaries.
- Keep feature modules focused and cohesive.
- Avoid circular dependencies.
- Put shared models/services in existing shared modules only when genuinely reused.
- Keep platform-specific code in appropriate platform modules.

## Dependency Injection Rules

- Prefer constructor injection for classes you own.
- Use protocols for services that need test doubles.
- Keep dependency containers small and explicit.
- Avoid global mutable singletons unless repository convention requires them.
- Use environment injection in SwiftUI according to repository standard.

## Testability Rules

- Create fakes/mocks through repository convention.
- Do not bind production services into tests.
- Keep test fixtures local and readable.
- Avoid network, Keychain, or database dependency in unit tests unless explicitly integration-level.

## Package Rules

- Do not add SPM/CocoaPods dependencies without approval.
- Keep package products and targets named consistently.
- Document public API changes across module boundaries.
- Check build impact across affected schemes.

## Testing

Common checks:

```bash
xcodebuild -scheme App -destination 'platform=iOS Simulator,name=iPhone 16' build
xcodebuild -scheme App -destination 'platform=iOS Simulator,name=iPhone 16' test
swift test
pod install
```

## Do Not Do

- Do not break module boundaries for convenience.
- Do not create hidden service locators without architecture approval.
- Do not introduce circular dependencies.
- Do not make public APIs broader than needed.

## Output Notes

When using this stack, report:

- Modules/targets/packages changed
- Dependency injection impact
- Public API impact
- Test double impact
- Build/test checks run
