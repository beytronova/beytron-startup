# Flutter Performance Guide

Use this guide when implementing or reviewing Flutter features with UI complexity, lists, animations, images, background work, startup impact, or reported jank.

## Performance Signals

Read this guide when:

- UI feels janky or frame drops are reported.
- Feature includes long lists, grids, charts, animations, images, maps, video, or background work.
- Changes touch app startup, navigation, expensive providers/blocs/notifiers, or large rebuild areas.

## Rules

- Prefer `const` constructors where useful and consistent.
- Keep build methods cheap and side-effect free.
- Avoid triggering network calls or heavy computation from `build`.
- Use lazy list builders for long lists.
- Use pagination or incremental loading for large datasets.
- Cache images intentionally and avoid oversized assets.
- Avoid unnecessary `setState`, provider, bloc, or notifier rebuilds.
- Keep expensive parsing/computation off the UI thread when needed.
- Dispose controllers, focus nodes, animation controllers, and subscriptions.

## Rebuild Control

Riverpod:

- Use fine-grained providers and selectors where appropriate.
- Avoid watching broad state when only one field is needed.

BLoC:

- Use `buildWhen`, `listenWhen`, or smaller widgets when needed.

Provider:

- Use `Selector` or `context.select` for granular rebuilds.

## Lists and Scroll

- Use `ListView.builder`, `GridView.builder`, or slivers for large collections.
- Avoid nesting unbounded scrollables without clear constraints.
- Use stable keys when item identity matters.
- Avoid expensive layout in every item build.

## Assets and Images

- Use appropriately sized image assets.
- Avoid decoding huge images for small UI areas.
- Use placeholders/error states for remote images.
- Document caching behavior when relevant.

## Profiling

When performance risk is meaningful, consider:

```bash
flutter run --profile
flutter build apk --profile
flutter build ios --profile
```

Use Flutter DevTools for:

- Frame rendering
- Rebuild tracking
- CPU profiling
- Memory growth
- Network inspection

## Output Format

```text
Performance review: PASS|RISK|BLOCKED
Risk areas: {list}
Optimizations applied: {list}
Profiling performed: {yes|no and why}
Remaining concerns: {list}
```

## Stop Conditions

Stop or escalate when:

- The feature requires performance validation but no target device/profile mode is available.
- Jank is reported but cannot be reproduced or measured.
- A change introduces unbounded loading, memory growth, or main-thread blocking.
