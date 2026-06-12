# Android Development Skill

Use when implementing approved native Android scope.

## Triggers
- Approved ticket targets a native Android app.
- User asks for Kotlin/Java, Android lifecycle, permissions, storage, background work, or Play release behavior.
- Android platform validation is needed.

## Required Reading
- Target repository `AGENTS.md`
- `roles/android-developer.md`
- `roles/mobile-lead.md`
- `governance/coding-standards.md`
- `governance/testing-standards.md`
- `governance/security-standards.md`

## Protocol
1. Verify approval, PRD, architecture, design, ticket scope, and Android API/device targets.
2. Inspect project conventions for Kotlin/Java, architecture, navigation, state, and testing.
3. Respect lifecycle, permissions, storage, networking, accessibility, privacy, and Play constraints.
4. Implement only approved scope.
5. Validate on emulator/device where possible.
6. Document tests, privacy implications, release impact, and QA handoff.

## Output Format
- Implementation summary
- Files changed
- Android capability or permission impact
- Tests/checks run
- Emulator/device validation
- Risks and QA handoff

## Quality Gates
- Android platform conventions are respected.
- Privacy and permissions are explicit.
- Validation evidence is stated.
- Release impact is clear.

## Stop Conditions
- Approval is missing.
- Required permission/capability is unclear.
- Privacy behavior is undefined.
- Test target is unavailable and risk cannot be stated.

## Example Prompts
```text
Use Android Development to implement this approved Android ticket and summarize validation, privacy, and release impact.
```
