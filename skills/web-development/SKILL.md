# Web Development Skill

Use when implementing approved web application scope.

## Triggers
- User asks to implement, fix, refactor, or test web app behavior.
- An approved Jira ticket targets a web repository.
- UI, API integration, routing, state, or frontend validation work is needed.

## Required Reading
- Target repository `AGENTS.md`
- `roles/web-developer.md`
- `workflows/backlog-to-development.md`
- `handoffs/architecture-to-development.md`
- `governance/coding-standards.md`
- `governance/testing-standards.md`

## Protocol
1. Verify `APPROVED_FOR_DEVELOPMENT`, ticket scope, PRD, architecture, and target repo.
2. Inspect existing framework, routing, state, styling, and test patterns.
3. Implement only approved scope.
4. Cover loading, empty, error, success, permission, and responsive states where relevant.
5. Run relevant checks or document why they could not run.
6. Produce implementation summary and development-to-QA handoff.

## Output Format
- Implementation summary
- Files changed
- Behavior changed
- Tests/checks run
- Tests skipped and why
- Risks
- QA handoff

## Quality Gates
- Existing patterns are preserved.
- UI states and accessibility are considered.
- Tests or validation are reported.
- Scope remains tied to ticket.

## Stop Conditions
- Approval is missing.
- Ticket scope is unclear.
- Architecture/API contract is missing.
- Test impact cannot be stated.

## Example Prompts
```text
Use Web Development to implement this approved Jira ticket and prepare QA handoff with tests and risks.
```
