---
name: web-development
description: Build approved web work with TypeScript, React, Next.js, Vite, component/service/hook boundaries, accessibility, tests, and build checks.
---

# Web Development

Use this skill when an approved ticket targets a web frontend or web app.

## Stack Guidance

- TypeScript by default.
- React, Next.js, or Vite according to repository stack.
- Components for UI composition.
- Hooks for reusable stateful behavior.
- Services or clients for external calls.
- Route/page files only for orchestration and data boundaries.

## Rules

- Follow existing repo conventions.
- Keep components focused and testable.
- Do not mix API calls directly into presentational components unless local pattern allows it.
- Include loading, empty, error, success, and accessibility states.
- Preserve responsive behavior.

## Verification

- Run the repo's lint, typecheck, test, and build commands when available.
- Add or update unit/component/E2E tests based on risk.

## Outputs

- Implementation summary.
- Test evidence.
- UI/state notes.
- QA handoff.
