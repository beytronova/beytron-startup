# Jira Backlog Skill

Use when converting PRD, design, and architecture into backlog-ready epics, stories, tasks, subtasks, and QA tasks.

## Triggers
- User asks to create Jira tickets or ticket drafts.
- PRD and architecture are ready for backlog.
- Work needs to be broken down for development.

## Ticket Structure Standards
Epics must include:
- Goal
- Scope
- Linked PRD
- Linked architecture
- Stories
- Acceptance criteria
- Risks

Stories/tasks must include:
- User story or system outcome
- Scope and non-scope
- Acceptance criteria
- Technical notes
- Test notes
- Dependencies
- Release impact

## Ticket Data Model
Use this structure for every ticket draft:

```text
Type: Epic / Story / Task / Subtask / QA / Release
Summary:
Parent:
Linked artifacts:
Description:
Acceptance criteria:
Technical notes:
Test notes:
Dependencies:
Labels:
Priority:
Release impact:
```

## Integration Standards
- Draft tickets first unless the user explicitly requests Jira issue creation.
- Preserve parent-child relationships when creating real Jira issues.
- Link related issues and blockers when supported.
- Keep ticket keys in later GitHub branch, commit, PR, QA, and release summaries.
- Do not create duplicate issues; search existing project when updating real Jira.

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

## Stop Conditions
- PRD or architecture is missing.
- Approval does not permit backlog work.
- Ticket scope is too broad.

## Example Prompts
```text
Use Jira Backlog to turn this PRD and architecture into Jira-ready epics, stories, QA tasks, and dependencies.
```
