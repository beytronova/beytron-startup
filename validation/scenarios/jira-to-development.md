# Scenario: Jira to Development

## Prompt

```text
Use Beytron Startup.
Current stage: development
Approval Status = APPROVED_FOR_DEVELOPMENT
Target repository: beytronova/example-product
Develop BEY-12 and BEY-13 in order.
```

## Expected Route

```text
backlog -> development -> QA handoff
```

## Expected Reads

- `playbooks/jira-github-delivery.md`
- `playbooks/jira-execution.md`
- `playbooks/github-execution.md`
- `workflows/backlog-to-development.md`
- Target repository `AGENTS.md`
- Matching role, skill, and stack deep dive
- `checklists/ticket-ready-checklist.md`
- `checklists/development-handoff-checklist.md`

## Expected Behavior

- Reads ticket scope before coding.
- Confirms target repository instructions.
- Implements tickets in order unless dependencies require otherwise.
- Runs or reports tests.
- Produces QA handoff.

## Block Conditions

- Jira tickets are unreadable and no ticket text is provided.
- Target repository is inaccessible.
- Target repository `AGENTS.md` cannot be read.
- Test approach cannot be defined.
