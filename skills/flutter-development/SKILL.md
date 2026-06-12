# Flutter Development Skill

Use when implementing approved cross-platform mobile scope with Flutter.

## Triggers
- Approved ticket targets a Flutter app.
- User asks to implement Flutter UI, state, navigation, persistence, or integrations.
- Cross-platform mobile behavior needs validation.

## Required Reading
- Target repository `AGENTS.md`
- `roles/flutter-developer.md`
- `roles/mobile-lead.md`
- `workflows/backlog-to-development.md`
- `governance/coding-standards.md`
- `governance/testing-standards.md`

## Protocol
1. Verify approval, PRD, architecture, design, ticket scope, and platform matrix.
2. Inspect existing Flutter architecture, state management, routing, and test style.
3. Keep business logic testable outside widgets.
4. Implement approved scope with platform differences, permissions, offline behavior, and performance in mind.
5. Run Flutter checks/tests where possible.
6. Document device/simulator validation, skipped checks, and QA handoff.

## Output Format
- Implementation summary
- Files changed
- State/navigation/data behavior
- Tests/checks run
- Device/simulator validation
- Risks and QA handoff

## Quality Gates
- Business logic is testable.
- Platform differences are documented.
- Critical flows have tests or validation notes.
- Approved scope is not exceeded.

## Stop Conditions
- Approval is missing.
- Platform requirements are unclear.
- Native capability is required but undesigned.
- Test impact cannot be stated.

## Example Prompts
```text
Use Flutter Development to implement this approved mobile ticket and produce platform validation notes.
```
