# Android Performance Guide

Use this guide when native Android work touches UI performance, startup, memory, lists, images, background work, battery, ANR risk, or reported jank.

## Performance Signals

Read this guide when:

- UI jank or frame drops are reported.
- Feature includes long lists, images, charts, maps, video, animations, or background work.
- Changes touch startup, dependency injection graph, database queries, network calls, or large UI states.

## General Rules

- Keep main thread work small.
- Avoid blocking calls on Main.
- Keep lifecycle and cancellation explicit.
- Avoid memory leaks from Context, Activity, Fragment, View, or long-running scopes.
- Avoid unbounded background work.
- Keep battery and network impact intentional.

## Compose Performance

- Keep Composables side-effect free except with proper effect APIs.
- Use stable state models where possible.
- Avoid creating expensive objects during recomposition.
- Use `remember` appropriately.
- Use lazy lists for large collections.
- Use keys for lazy list item identity when needed.
- Avoid broad state reads that recompose large trees.

## XML/View Performance

- Avoid deep unnecessary view hierarchies.
- Use RecyclerView/ListAdapter/DiffUtil for large lists.
- Avoid heavy work in `onBindViewHolder`.
- Release view bindings according to lifecycle.

## Startup

- Avoid eager initialization of expensive services.
- Defer non-critical work.
- Watch dependency injection graph cost.
- Use baseline profiles when repository supports them.

## Database and Network

- Avoid large unbounded queries.
- Use indexes where needed.
- Paginate large datasets.
- Avoid repeated network calls from UI lifecycle events.

## Profiling

Use repository tools first. Common options:

```bash
./gradlew assembleRelease
./gradlew connectedAndroidTest
```

Consider Android Studio profilers for:

- CPU
- Memory
- Network
- Energy
- Startup traces

## Output Format

```text
Android performance review: PASS|RISK|BLOCKED
Risk areas: {list}
Optimizations applied: {list}
Profiling performed: {yes|no and why}
Remaining concerns: {list}
```

## Stop Conditions

Stop or escalate when:

- Performance-sensitive work cannot be validated on a representative device/emulator.
- A change introduces main-thread blocking, unbounded loading, ANR risk, memory leak risk, or battery-heavy background work.
