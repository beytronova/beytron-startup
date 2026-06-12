# iOS Performance Guide

Use this guide when iOS work touches UI performance, startup, memory, scrolling, images, background work, or reported jank.

## Performance Signals

Read this guide when:

- UI jank or slow scrolling is reported.
- Feature includes long lists, images, charts, maps, video, animations, or background work.
- Changes touch startup, dependency injection, persistence, networking, or large UI states.

## General Rules

- Keep main thread work small.
- Avoid blocking MainActor with heavy work.
- Keep async cancellation explicit.
- Avoid retain cycles from closures, timers, delegates, tasks, and Combine subscriptions.
- Avoid unbounded background work.
- Keep memory and battery impact intentional.

## SwiftUI Performance

- Keep view bodies cheap.
- Avoid expensive work during body evaluation.
- Keep state scoped narrowly.
- Avoid broad observable objects that refresh large view trees unnecessarily.
- Use lazy containers for large collections.
- Keep image loading/caching intentional.

## UIKit Performance

- Keep cell configuration cheap.
- Use reusable cells correctly.
- Avoid deep unnecessary view hierarchies.
- Avoid duplicate lifecycle-triggered work.

## Startup

- Avoid eager initialization of expensive services.
- Defer non-critical work.
- Watch dependency graph and package initialization cost.

## Instruments

Use Instruments or Xcode tools when performance risk is meaningful:

- Time Profiler
- Allocations
- Leaks
- Memory Graph
- Network
- Energy Log

## Output Format

```text
iOS performance review: PASS|RISK|BLOCKED
Risk areas: {list}
Optimizations applied: {list}
Profiling performed: {yes|no and why}
Remaining concerns: {list}
```

## Stop Conditions

Stop or escalate when:

- Performance-sensitive work cannot be validated on representative simulator/device.
- A change introduces main-thread blocking, memory leak risk, runaway tasks, or unbounded loading.
