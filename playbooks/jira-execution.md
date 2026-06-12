# Jira Execution Playbook

Use this playbook when Codex needs to read, create, update, or transition Jira issues.

## Required Reads

- `config/tool-access.yaml`
- `integrations/jira.md`
- Relevant workflow under `workflows/`
- `skills/jira-backlog/SKILL.md`
- `governance/definition-of-ready.md`

## Allowed Actions by Approval

### No Approval

Allowed:

- Explain expected Jira structure.
- Draft Jira issues in Markdown.
- Identify missing fields.

Not allowed:

- Create, update, transition, assign, or delete Jira issues.

### APPROVED_FOR_JIRA_CREATION

Allowed:

- Create approved epics, stories, tasks, and bugs.
- Add labels, components, acceptance criteria, dependencies, and links when provided.

Required before action:

- Approved ticket drafts
- Project key
- Issue type mapping
- Summary and description
- Acceptance criteria
- Priority or default priority

### APPROVED_FOR_DEVELOPMENT

Allowed:

- Read ticket details.
- Add implementation comments when requested.
- Link GitHub PRs to tickets when requested.

Not allowed:

- Change ticket scope without user approval.

### APPROVED_FOR_RELEASE

Allowed:

- Transition release-related issues when release workflow permits it.
- Add release notes or deployment evidence when requested.

## Jira Field Standard

Every story or task should include:

- Summary
- Problem or goal
- User value
- Scope
- Out of scope
- Acceptance criteria
- Technical notes
- Design references
- PRD reference
- Architecture reference
- Test notes
- Dependencies
- Definition of Done

Recommended labels:

- `beytron-startup`
- stage label such as `discovery`, `prd`, `architecture`, `development`, `qa`, `release`
- platform label such as `web`, `backend`, `flutter`, `ios`, `android`

## Duplicate Check

Before creating issues:

1. Search by summary keywords.
2. Search by idea slug or feature name.
3. Search by PRD or architecture reference.
4. If possible duplicates exist, report them and stop unless user confirms creation.

## Creation Sequence

1. Create or identify Epic.
2. Create Stories under Epic.
3. Create Tasks/Subtasks when needed.
4. Link dependencies.
5. Add acceptance criteria and test notes.
6. Return created issue keys and URLs.

## Update Sequence

1. Read current issue.
2. Compare requested change with existing scope.
3. Identify scope, acceptance, dependency, or test impact.
4. Ask for approval if the change materially changes scope.
5. Update only approved fields.
6. Return before/after summary.

## Failure Handling

If Jira is unavailable:

- Produce Markdown ticket drafts.
- Explain that real issue creation was not performed.
- List the exact fields ready for creation.

If required fields are missing:

- Stop.
- Return a blocker list.
- Do not create partial issues unless the user explicitly accepts placeholders.

## Final Response Format

```text
Jira action: {read|draft|create|update|transition}
Approval: {status}
Project: {key}
Issues affected: {keys or drafts}
Duplicate check: {done|blocked|not available}
Created/updated: {list}
Blocked: {missing fields or permissions}
Next step: {specific action}
```
