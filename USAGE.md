# Usage

This guide gives practical commands and prompts for running Beytron Startup with Codex.

## Universal Prompt Pattern

```text
Use Beytron Startup.
Current stage: {idea|discovery|PRD|design|architecture|backlog|development|QA|release|growth}
Approval Status = {status}
Goal: {what you want}
Inputs: {links, files, tickets, repository, constraints}
```

## Idea to Research

```text
Use Beytron Startup.
Current stage: idea
Approval Status = APPROVED_FOR_RESEARCH
Idea: {raw idea}
Research this idea and prepare it for PRD.
```

Expected outputs:

- Discovery summary
- Assumptions
- Market/user research notes
- Risks
- Open questions
- PRD readiness result

## Research to PRD

```text
Use Beytron Startup.
Current stage: discovery
Approval Status = APPROVED_FOR_RESEARCH
Convert the discovery artifact into a PRD using the PRD template.
```

Expected outputs:

- PRD draft
- Goals and non-goals
- User stories
- Acceptance criteria
- Metrics
- Risks and dependencies

## PRD to Architecture

```text
Use Beytron Startup.
Current stage: PRD
Approval Status = APPROVED_FOR_RESEARCH
Create architecture from this PRD.
```

Expected outputs:

- Architecture draft
- Technical approach
- API/data impact
- Security notes
- Test strategy

## PRD to Jira Drafts

```text
Use Beytron Startup.
Current stage: backlog
Approval Status = APPROVED_FOR_RESEARCH
Create Jira ticket drafts from this PRD and architecture. Do not create real Jira issues yet.
```

Expected outputs:

- Epic draft
- Story/task drafts
- Acceptance criteria
- Dependencies
- Suggested execution order

## Create Real Jira Issues

```text
Use Beytron Startup.
Approval Status = APPROVED_FOR_JIRA_CREATION
Create Jira issues from these approved ticket drafts.
```

Codex must read:

- `playbooks/jira-execution.md`
- `integrations/jira.md`
- `config/tool-access.yaml`

## Development from Jira Tickets

```text
Use Beytron Startup.
Current stage: development
Approval Status = APPROVED_FOR_DEVELOPMENT
Target repository: {owner/repo}
Develop tickets {TICKET-1}, {TICKET-2} in order.
```

Codex must verify:

- Ticket scope
- Target repository
- Target repository `AGENTS.md`
- PRD and architecture references
- Correct role, skill, stack deep dive
- Test commands

## Repo Bootstrap

```text
Use Beytron Startup.
Current stage: repo-bootstrap
Approval Status = APPROVED_FOR_REPO_CREATION
Create a product repository proposal for {idea slug}. Do not create the repository until I explicitly approve execution.
```

Codex must read:

- `repo-bootstrap/README.md`
- `repo-bootstrap/product-repo-bootstrap.md`
- `checklists/repo-bootstrap-checklist.md`

## Release Preparation

```text
Use Beytron Startup.
Current stage: release
Approval Status = APPROVED_FOR_RELEASE_PREPARATION
Prepare release notes, rollback plan, and monitoring plan. Do not publish the release.
```

Publishing requires:

```text
Approval Status = APPROVED_FOR_RELEASE
```

## Revise Existing Artifacts

```text
Use Beytron Startup.
Revise the existing {PRD|architecture|ticket drafts|release plan} based on this new information: {change request}
Keep traceability to the original artifact and list what changed.
```

Expected outputs:

- Source artifact read
- Change summary
- Updated artifact
- Impacted workflows/tickets
- New risks or approvals needed

## Good Final Response Format

```text
Route used: {stage -> workflow}
Role used: {role}
Skill used: {skill}
Checklist used: {checklist}
Artifacts changed: {files or drafts}
Approval status: {status}
Blockers: {if any}
Next step: {specific next action}
```
