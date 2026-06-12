# Jira Ticket to Pull Request Golden Path

Use this example when the user gives approved Jira tickets and asks Codex to implement them in order.

## Example User Prompt

```text
Approval Status = APPROVED_FOR_DEVELOPMENT
Develop BEY-12 and BEY-13 in order.
```

## Route

- Stage: development
- Workflow: `workflows/backlog-to-development.md`
- Primary role: developer role matching the repository stack
- Supporting roles: Architect, QA Developer, Security Reviewer when needed
- Required checklist: `checklists/ticket-ready-checklist.md`

## Preconditions

Before implementation starts, Codex must confirm:

- Approval status is `APPROVED_FOR_DEVELOPMENT`.
- Jira ticket IDs are provided.
- Ticket scope, acceptance criteria, and dependencies are readable.
- Target product repository is known.
- Target repository `AGENTS.md` has been read.
- PRD and architecture references are available or explicitly waived.
- The correct implementation skill and stack deep dive have been selected.

## Step 1: Read Delivery Context

Read:

- `config/workflow-map.yaml`
- `config/role-skill-map.yaml`
- `config/tool-access.yaml`
- `workflows/backlog-to-development.md`
- `governance/definition-of-ready.md`
- `governance/coding-standards.md`
- `governance/testing-standards.md`

If Jira access is available, read each ticket. If Jira access is unavailable, ask the user for ticket text or a local artifact.

## Step 2: Order Tickets

For each ticket, capture:

- Ticket ID
- Goal
- Acceptance criteria
- Dependencies
- Affected area
- Test expectations
- Risk level

Rules:

- Implement tickets in the requested order unless dependencies require a different order.
- If order changes, explain the reason before coding.
- Do not merge unrelated cleanup into the ticket.

## Step 3: Select Developer Role and Skill

Examples:

- Next.js or React repository: `roles/web-developer.md` and `skills/web-development/SKILL.md`
- Flutter repository: `roles/flutter-developer.md` and `skills/flutter-development/SKILL.md`
- iOS repository: `roles/ios-developer.md` and `skills/ios-development/SKILL.md`
- Android repository: `roles/android-developer.md` and `skills/android-development/SKILL.md`
- API/backend repository: `roles/backend-developer.md` and `skills/backend-development/SKILL.md`

Then read the matching stack deep dive under `skills/*/stacks/` when present.

## Step 4: Implement Ticket 1

Process:

1. Inspect current code and tests.
2. Make the smallest coherent change that satisfies the ticket.
3. Add or update tests based on acceptance criteria.
4. Run targeted tests and lint/build commands appropriate for the stack.
5. Record evidence.

Output after ticket 1:

- Files changed
- Tests run
- Acceptance criteria coverage
- Remaining risks

## Step 5: Implement Ticket 2

Repeat the same process. Before starting, check whether ticket 1 changed assumptions or shared code.

## Step 6: QA Handoff

Read:

- `handoffs/development-to-qa.md`
- `checklists/development-handoff-checklist.md`

Produce:

- Summary of implemented tickets
- Acceptance criteria mapping
- Test evidence
- Known limitations
- Suggested QA regression scope

## Step 7: Pull Request

Only create a branch or PR if GitHub permissions and workflow approval allow it.

PR body should include:

- Jira tickets
- Summary
- Test evidence
- Screenshots or recordings when UI changed
- Risk and rollback notes
- Checklist status

## Expected Final Response Shape

```text
Implemented BEY-12 and BEY-13 in order.

Changed:
- Payment forecast service
- Subscription prediction UI

Verified:
- npm test -- subscription-prediction
- npm run lint

QA handoff:
- Acceptance criteria covered
- Regression focus: subscription list, empty state, forecast refresh

PR: created as draft / not created because approval is missing
```
