# Approval Statuses

This file is the canonical approval status policy for Beytron Startup.

All workflows, playbooks, examples, templates, repo bootstrap flows, Jira actions, GitHub actions, development actions, security risk acceptance, and release actions must use these statuses exactly.

If another file conflicts with this policy, this file wins.

## Status List

- `WAITING`
- `APPROVED_FOR_RESEARCH`
- `APPROVED_FOR_JIRA_CREATION`
- `APPROVED_FOR_REPO_CREATION`
- `APPROVED_FOR_DEVELOPMENT`
- `APPROVED_FOR_RELEASE_PREPARATION`
- `APPROVED_FOR_RELEASE`
- `APPROVED_FOR_SECURITY_RISK_ACCEPTANCE`
- `REJECTED`

## WAITING

Default state for new ideas, incomplete requests, and unapproved work.

Allowed:

- Ask clarifying questions.
- Summarize provided information.
- Draft a non-executed plan.
- Identify missing artifacts and approvals.

Blocked:

- Research execution.
- Jira issue creation.
- GitHub repository creation.
- Branch, commit, or PR creation.
- Product code development.
- Release publishing.

Required to move forward:

- User gives a specific approval status appropriate to the next action.

Next statuses:

- `APPROVED_FOR_RESEARCH`
- `REJECTED`

## APPROVED_FOR_RESEARCH

Allows idea discovery, research, PRD, architecture, design planning, ticket drafting, and non-executed planning artifacts.

Allowed:

- Web or source research when tool access permits it.
- Discovery artifacts.
- PRD drafts.
- Design briefs.
- Architecture drafts.
- Jira ticket drafts in Markdown.
- Risk analysis.
- Security review drafts.

Blocked:

- Real Jira issue creation.
- Product repository creation.
- Product code development.
- GitHub branch, commit, or PR creation.
- Release publishing.

Required artifacts:

- Raw idea or source request.
- Scope assumptions.
- Research or artifact goal.

Next statuses:

- `APPROVED_FOR_JIRA_CREATION`
- `APPROVED_FOR_REPO_CREATION`
- `APPROVED_FOR_DEVELOPMENT`
- `REJECTED`

## APPROVED_FOR_JIRA_CREATION

Allows approved ticket drafts to become real Jira issues.

Allowed:

- Create Jira epics, stories, tasks, bugs, and subtasks from approved drafts.
- Add labels, components, priority, acceptance criteria, dependencies, and links when provided.
- Link Jira issues to source artifacts.

Blocked:

- Product repository creation unless separately approved.
- Product code development.
- GitHub branch, commit, or PR creation unless development approval also exists.
- Release publishing.

Required artifacts:

- Approved ticket drafts.
- Jira project key.
- Issue type mapping.
- Acceptance criteria.
- Source PRD or architecture reference when applicable.

Next statuses:

- `APPROVED_FOR_REPO_CREATION`
- `APPROVED_FOR_DEVELOPMENT`
- `REJECTED`

## APPROVED_FOR_REPO_CREATION

Allows an approved idea to become a product repository proposal or repository creation action.

Allowed:

- Prepare product repository bootstrap proposal.
- Create product repository only when the user explicitly asks for execution and GitHub access permits it.
- Add approved initial documentation files.
- Link source idea, PRD, architecture, ticket drafts, and approval artifact.

Blocked:

- Product code development.
- Feature branches for implementation.
- Pull requests for product code.
- Release publishing.

Required artifacts:

- Approved idea.
- PRD.
- Architecture.
- Ticket drafts or backlog plan.
- Repository owner, name, and visibility.
- Repo bootstrap checklist pass.

Next statuses:

- `APPROVED_FOR_DEVELOPMENT`
- `REJECTED`

## APPROVED_FOR_DEVELOPMENT

Allows approved implementation work inside the target product repository.

Allowed:

- Read Jira tickets and source artifacts.
- Create or use a development branch.
- Implement approved ticket scope.
- Add or update tests.
- Commit changes when workflow and tool access permit it.
- Open draft PR when requested or workflow permits it.
- Prepare QA handoff.

Blocked:

- Scope expansion beyond approved tickets.
- Product repository creation unless separately approved.
- Release publishing.
- Security risk acceptance without explicit risk approval.

Required artifacts:

- Approved Jira ticket or equivalent approved task.
- PRD reference or explicit waiver.
- Architecture reference or explicit waiver.
- Target product repository.
- Target repository `AGENTS.md` read.
- Test approach.

Next statuses:

- `APPROVED_FOR_RELEASE_PREPARATION`
- `APPROVED_FOR_SECURITY_RISK_ACCEPTANCE`
- `REJECTED`

## APPROVED_FOR_RELEASE_PREPARATION

Allows release artifacts to be prepared without publishing.

Allowed:

- Prepare release notes.
- Prepare rollback plan.
- Prepare monitoring plan.
- Prepare release checklist.
- Summarize QA evidence and known risks.

Blocked:

- Publishing releases.
- Creating tags.
- Marketplace/package publication.
- Production deployment.

Required artifacts:

- QA evidence.
- Known risks.
- Rollback plan draft.
- Release scope.

Next statuses:

- `APPROVED_FOR_RELEASE`
- `APPROVED_FOR_SECURITY_RISK_ACCEPTANCE`
- `REJECTED`

## APPROVED_FOR_RELEASE

Allows release execution or publication when release gates pass.

Allowed:

- Publish release when workflow and tool access permit it.
- Create release tags or GitHub releases when approved.
- Add deployment evidence.
- Transition release-related tickets when approved.

Blocked:

- Releasing with failed QA gate unless explicit risk acceptance exists.
- Releasing with unresolved critical security blockers.
- Releasing scope not included in the approved release plan.

Required artifacts:

- Release checklist pass.
- QA evidence.
- Rollback plan.
- Monitoring plan.
- Known risk review.

Next statuses:

- `APPROVED_FOR_SECURITY_RISK_ACCEPTANCE`
- `REJECTED`

## APPROVED_FOR_SECURITY_RISK_ACCEPTANCE

Allows explicitly documented residual security risk to be accepted by the owner.

Allowed:

- Record residual risk acceptance.
- Proceed with a workflow only for the accepted risk and scope.
- Document mitigation follow-ups.

Blocked:

- Blanket acceptance of unknown risks.
- Acceptance without documented owner approval.
- Acceptance of risks outside the described scope.
- Secret exposure without rotation/remediation.

Required artifacts:

- Threat model or security review.
- Data classification.
- Risk description.
- Mitigation options.
- Owner approval.
- Expiration or revisit condition when applicable.

Next statuses:

- `APPROVED_FOR_DEVELOPMENT`
- `APPROVED_FOR_RELEASE_PREPARATION`
- `APPROVED_FOR_RELEASE`
- `REJECTED`

## REJECTED

Stops the workflow.

Allowed:

- Summarize why work stopped.
- Archive or mark artifacts as rejected.
- Suggest what would be needed to reopen later.

Blocked:

- Research execution.
- Jira issue creation.
- Repository creation.
- Product code development.
- Release publishing.

Required to move forward:

- New user instruction with a new approval status.

## Output Format

Every approval-sensitive response should include:

```text
Approval status: {status}
Allowed actions: {list}
Blocked actions: {list}
Required artifacts: {list}
Next valid statuses: {list}
```
