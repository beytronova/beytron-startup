# Jira to GitHub Delivery Playbook

Use this playbook when approved Jira tickets need to become GitHub implementation work.

## Required Reads

- `playbooks/jira-execution.md`
- `playbooks/github-execution.md`
- `examples/jira-ticket-to-pr-example.md`
- `workflows/backlog-to-development.md`
- `handoffs/development-to-qa.md`

## Preconditions

- `Approval Status = APPROVED_FOR_DEVELOPMENT`
- Jira ticket IDs are known.
- Target repository is known.
- Ticket scope and acceptance criteria are readable.
- PRD and architecture references exist or are explicitly waived.
- Target repository `AGENTS.md` has been read.

## Delivery Sequence

1. Read all requested Jira tickets.
2. Confirm implementation order.
3. Identify target repository and stack.
4. Read matching role, skill, and stack deep dive.
5. Inspect code and tests.
6. Implement ticket 1.
7. Verify ticket 1.
8. Implement ticket 2 and later tickets in order.
9. Verify combined behavior.
10. Prepare QA handoff.
11. Open PR if approved.
12. Link PR back to Jira if approved.

## Ticket Ordering Rules

- Follow user-provided order by default.
- Change order only when dependency analysis proves it is necessary.
- Report order changes before coding.
- Do not combine unrelated tickets into one implementation unless the user approves.

## Scope Control

Allowed:

- Changes required by ticket acceptance criteria.
- Tests required to verify the ticket.
- Small supporting refactors that reduce risk and stay local.

Not allowed:

- New features outside the ticket.
- Repository-wide rewrites.
- Silent ticket scope expansion.
- Release publishing.

## Evidence Required

For each ticket, capture:

- Files changed
- Acceptance criteria covered
- Tests added or updated
- Commands run
- Known risks
- QA notes

## Final Response Format

```text
Delivery route: Jira -> GitHub -> QA
Approval: APPROVED_FOR_DEVELOPMENT
Tickets completed: {keys}
Repository: {owner/repo}
Branch: {branch}
PR: {url or not created}
Verification: {commands}
QA handoff: {summary}
Jira updates: {done|not approved|blocked}
Blockers: {if any}
```
