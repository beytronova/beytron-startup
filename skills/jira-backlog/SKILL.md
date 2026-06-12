# Jira Backlog Skill

Use when converting PRD, design, and architecture into backlog-ready epics, stories, tasks, subtasks, and QA tasks.

## Triggers
- User asks to create Jira tickets or ticket drafts.
- PRD and architecture are ready for backlog.
- Work needs to be broken down for development.

## Required Reading
- `workflows/architecture-to-backlog.md`
- `templates/JIRA_EPIC.template.md`
- `templates/JIRA_STORY.template.md`
- `governance/definition-of-ready.md`
- `governance/approval-rules.md`

## Protocol
1. Verify PRD, architecture, design notes, and approval state.
2. Split scope into epics, stories, tasks, subtasks, QA tasks, and release tasks.
3. Keep each ticket small, testable, and traceable to acceptance criteria.
4. Add dependencies, technical notes, test notes, and release impact.
5. Create ticket drafts first unless the user explicitly asks to create real Jira issues.
6. When creating real Jira issues, preserve issue links, parent relationships, and dependency order.

## Output Format
- Epic draft
- Story/task drafts
- QA task drafts
- Dependency map
- Definition of Ready status

## Quality Gates
- Every ticket traces to PRD and architecture.
- Acceptance criteria are testable.
- Dependencies are explicit.
- QA and release impact are included.

## Stop Conditions
- PRD or architecture is missing.
- Approval does not permit backlog work.
- Ticket scope is too broad.

## Example Prompts
```text
Use Jira Backlog to turn this PRD and architecture into Jira-ready epics, stories, QA tasks, and dependencies.
```
