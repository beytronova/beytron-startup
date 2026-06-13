---
name: jira-backlog
description: Transform PRD and architecture into Jira-ready Epics, Stories, Tasks, Subtasks, acceptance criteria, dependencies, labels, and Kanban sequencing.
---

# Jira Backlog

Use this skill when approved planning artifacts need Jira ticket drafts or Jira issue creation guidance.

## Required Inputs

- PRD.
- Architecture.
- Acceptance criteria.
- Approval status.
- Project key and board conventions.

## Ticket Model

- Epic for product capability.
- Story for user-visible behavior.
- Task for technical implementation.
- Subtask for QA, automation, release, or platform-specific work.
- Bug for defects.

## Rules

- Draft tickets before creating Jira issues unless explicit creation is approved.
- Keep each ticket independently testable.
- Include acceptance criteria and QA notes.
- Link dependencies and blockers.
- Do not move to development without `APPROVED_FOR_DEVELOPMENT`.

## Outputs

- Jira ticket drafts.
- Kanban sequencing.
- Dependency map.
- QA handoff notes.
