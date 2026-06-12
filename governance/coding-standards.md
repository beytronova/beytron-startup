# Coding Standards

## Core Rules

- Follow the target repository's `AGENTS.md` and existing conventions first.
- Keep changes scoped to approved tickets.
- Prefer clear, testable code over premature abstraction.
- Do not introduce dependencies without justification.
- Do not mix unrelated refactors with feature or bug work.
- Keep docs, tests, and release notes aligned with behavior changes.
- Preserve public contracts unless contract change is explicitly approved.

## Implementation Expectations

- Read the surrounding code before editing.
- Reuse existing helpers, styles, and patterns.
- Handle error, empty, loading, permission, and edge states when user-facing.
- Document migration, data, integration, or rollback impact when relevant.
- Keep secrets, credentials, and environment-specific values out of code.

## Review Checklist

- [ ] Approved scope only.
- [ ] Existing patterns respected.
- [ ] Error and edge cases handled.
- [ ] Tests or validation notes included.
- [ ] Security/privacy impact considered.
- [ ] Release impact stated.

## Stop Conditions

- Scope is unclear.
- Repository instructions are missing or conflict with request.
- Required contract or dependency is unknown.
- Test impact cannot be stated.
