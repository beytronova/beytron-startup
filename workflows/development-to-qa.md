# Development to QA

## Purpose
Move implementation into validation with clear test scope, evidence, and release readiness recommendation.

## Trigger
Development work is complete or ready for validation.

## Required Approval
- Minimum: `APPROVED_FOR_QA`
- If approval is not explicit but the user requests QA directly, mark status as user-requested QA.

## Required Roles
- QA Developer
- Automation Developer when repeatable checks are valuable
- Implementing developer
- Product when acceptance criteria are ambiguous

## Required Inputs
- Ticket scope
- Implementation summary
- Changed areas
- Tests run
- Tests skipped
- Known risks
- Environment details

## Steps
1. Read implementation summary and ticket scope.
2. Map acceptance criteria to tests.
3. Build or update test plan.
4. Run available checks or document blockers.
5. Record blockers, skipped tests, bugs, evidence, and release readiness.

## Outputs
- QA report
- Test cases
- Bug reports
- Release readiness recommendation
- Automation opportunities

## Artifact Target
- QA notes, test plan, or Jira comments/tasks.

## Tool Usage
- Atlassian/Jira tools may be used for bug/task creation when requested.
- Test automation tools may be used when in the target repo.

## Failure Handling
- If implementation summary is missing, return to developer role.
- If acceptance criteria are missing, return to Product.
- If critical blockers exist, mark release not ready.
