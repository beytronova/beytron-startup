# iOS Development Skill

Use when implementing approved native iOS scope.

## Triggers
- Approved ticket targets a native iOS app.
- User asks for Swift, SwiftUI, UIKit, App Intents, permissions, or iOS platform behavior.
- iOS release or privacy impact must be evaluated.

## Required Reading
- Target repository `AGENTS.md`
- `roles/ios-developer.md`
- `roles/mobile-lead.md`
- `governance/coding-standards.md`
- `governance/testing-standards.md`
- `governance/security-standards.md`

## Protocol
1. Verify approval, PRD, architecture, design, ticket scope, and iOS targets.
2. Inspect project conventions for Swift, SwiftUI/UIKit, navigation, state, and testing.
3. Respect lifecycle, permissions, storage, networking, accessibility, privacy, and App Store constraints.
4. Implement only approved scope.
5. Validate on simulator/device where possible.
6. Document tests, privacy implications, release impact, and QA handoff.

## Output Format
- Implementation summary
- Files changed
- iOS capability or permission impact
- Tests/checks run
- Simulator/device validation
- Risks and QA handoff

## Quality Gates
- Apple platform conventions are respected.
- Privacy and permissions are explicit.
- Validation evidence is stated.
- Release impact is clear.

## Stop Conditions
- Approval is missing.
- Required entitlement/capability is unclear.
- Privacy behavior is undefined.
- Test target is unavailable and risk cannot be stated.

## Example Prompts
```text
Use iOS Development to implement this approved iOS ticket and summarize validation, privacy, and release impact.
```
