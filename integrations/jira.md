# Jira Integration

## Purpose
Use Jira to search, draft, create, update, link, and comment on backlog items that trace product intent to implementation, QA, and release work.

## Required Access
- Read access to Jira projects, issue types, fields, statuses, and existing issues.
- Write access for issue creation, edits, transitions, comments, and links when explicitly approved.
- Access to project metadata such as epics, components, labels, versions, and priorities when used.

## Authentication
Jira access must come from an authorized Atlassian connector, app, or approved API credential.

Before write operations, verify:

- Jira site/cloud
- Project key
- Issue type
- Required fields
- Parent issue when applicable
- Approval state

## Inputs
- PRD
- Architecture
- Design brief when UI exists
- Acceptance criteria
- Technical notes
- Test notes
- Dependencies
- Release impact
- Project key
- Approval status

## Outputs
- Issue key
- Issue URL
- Parent/child relationships
- Linked dependencies
- Status
- Created/updated fields
- Comments added
- Creation or update summary

## Workflow Usage

### Drafting
Allowed in:

- `workflows/architecture-to-backlog.md`

Drafting requires `APPROVED_FOR_BACKLOG` or explicit user request.

### Real Issue Creation
Allowed only when:

- User explicitly asks to create Jira issues, or
- Workflow approval permits real issue creation

### QA and Release Updates
Allowed in:

- `workflows/development-to-qa.md`
- `workflows/qa-to-release.md`

Only update issues with QA results, blockers, release readiness, or release references when requested or approved.

## Ticket Standards
Each Jira issue should include:

- Summary
- Description
- Scope/non-scope
- Acceptance criteria
- Technical notes
- Test notes
- Dependencies
- Labels/components when available
- Release impact
- Linked PRD/architecture references

## Failure Handling
- If project key is missing, stop and ask for it.
- If required fields are unknown, inspect project metadata or ask for missing values.
- If duplicate issues may exist, search before creating.
- If issue creation fails, return the draft and failure reason.
- If approval is missing, produce ticket drafts only.
