# iOS UIKit Stack Deep Dive

Use this when an iOS repository uses UIKit, ViewControllers, Storyboards, XIBs, UIKit navigation, table views, or collection views.

## Stack Signals

- Code uses `UIViewController`, `UIView`, `UITableView`, `UICollectionView`, `UINavigationController`, `UITabBarController`, Storyboards, or XIBs.
- UI files include `.storyboard` or `.xib`.
- Architecture uses coordinators, delegates, data sources, or UIKit lifecycle methods.

## Primary Language

- Swift.
- Objective-C only for legacy or approved bridging work.

## File Structure Rules

- Keep ViewControllers focused on rendering, lifecycle, and user interaction.
- Keep business logic in view models, use cases, services, or repositories.
- Keep networking, persistence, permissions, and Keychain access behind services.
- Keep table/collection view cells focused on presentation.
- Keep coordinators/navigation separate when repository uses coordinator pattern.

## Lifecycle Rules

- Use lifecycle methods intentionally: `viewDidLoad`, `viewWillAppear`, `viewDidAppear`, `viewWillDisappear`.
- Avoid starting duplicate work on repeated lifecycle events.
- Cancel tasks/subscriptions when the view disappears or deinitializes when needed.
- Avoid retain cycles in closures, delegates, timers, and observers.

## Table/Collection Rules

- Use diffable data sources when repository convention supports them.
- Keep cell configuration cheap and deterministic.
- Reuse cells safely.
- Handle empty, loading, error, and pagination states.

## Navigation Rules

- Follow repository navigation pattern.
- Keep route construction testable when coordinators are used.
- Avoid hidden navigation side effects from business logic.

## Testing

Common checks:

```bash
xcodebuild -scheme App -destination 'platform=iOS Simulator,name=iPhone 16' build
xcodebuild -scheme App -destination 'platform=iOS Simulator,name=iPhone 16' test
```

Use unit tests for view models and UI tests for critical flows when the repository supports them.

## Do Not Do

- Do not put network or persistence calls directly in ViewControllers.
- Do not force unwrap normal data flow.
- Do not retain views, view controllers, delegates, observers, or subscriptions longer than needed.
- Do not add entitlements or capabilities without approval.

## Output Notes

When using this stack, report:

- ViewControllers/views/storyboards changed
- Navigation/coordinator impact
- Table/collection impact
- Lifecycle and memory notes
- Tests/checks run
