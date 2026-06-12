# Architecture to Backlog

## Purpose
Convert PRD, design, and architecture into implementation-ready backlog items.

## Trigger
PRD and architecture exist and the user wants Jira tickets, issue drafts, or implementation planning.

## Required Approval
- Minimum: `APPROVED_FOR_BACKLOG`
- Real Jira issue creation requires explicit user request or approval.

## Required Roles
- Product
- Architect
- QA Developer
- Relevant developer roles
- DevOps Release when release impact exists

## Required Inputs
- PRD
- Architecture
- Design brief when UI exists
- Acceptance criteria
- Technical constraints
- Approval status

## Steps
1. Read PRD, design, and architecture.
2. Split work into epics, stories, tasks, subtasks, QA tasks, and release tasks.
3. Add acceptance criteria, technical notes, dependencies, test notes, and release impact.
4. Confirm Definition of Ready.
5. Produce Jira drafts or create Jira issues only when explicitly requested.

## Outputs
- Epic drafts
- Story/task drafts
- QA task drafts
- Dependency map
- Definition of Ready status

## Artifact Target
- Backlog draft or Jira issue set.

## Tool Usage
- Atlassian/Jira tools may be used only when real issue creation or lookup is requested.
- GitHub tools are not needed unless linking target repositories.

## Failure Handling
- If tickets do not trace to acceptance criteria, revise before creating issues.
- If dependencies are unknown, mark tickets blocked.
- If approval is missing, produce drafts only and mark pending.
