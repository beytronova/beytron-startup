# Idea to Release Golden Path

Use this example when a user brings a raw product idea and wants to move it toward a releasable product change.

## Example User Prompt

```text
I have an idea for a budgeting mobile app feature that predicts upcoming subscriptions.
Research it, turn it into a PRD, create ticket drafts, and prepare it for development approval.
```

## Route

- Stage: idea
- Workflow map entry: `idea -> discovery -> PRD -> design -> architecture -> backlog -> development -> QA -> release -> growth`
- Primary roles: Product, Product Designer, Architect, Developer, QA, DevOps Release, Growth SEO
- Primary skills: product-discovery, prd-writing, ux-product-design, architecture, jira-backlog, implementation skill by stack, qa-testing, release-management, growth-seo

## Required Source Artifacts

- Raw idea or problem statement
- Target user or market assumption
- Known business constraints
- Approval status
- Target product repository, if it already exists

## Step 1: Discovery

Read:

- `config/workflow-map.yaml`
- `config/role-skill-map.yaml`
- `workflows/idea-to-discovery.md`
- `roles/product.md`
- `skills/product-discovery/SKILL.md`
- `checklists/discovery-checklist.md`

Output:

- Problem statement
- Target user hypothesis
- Market and competitor notes
- Assumptions
- Risks
- Open questions
- Recommendation for PRD readiness

Stop if:

- The idea has no clear user, problem, or expected outcome.
- Research approval is missing when required.

## Step 2: PRD

Read:

- `workflows/discovery-to-prd.md`
- `templates/PRD.template.md`
- `skills/prd-writing/SKILL.md`
- `checklists/prd-checklist.md`

Output:

- PRD with goals, non-goals, user stories, acceptance criteria, metrics, dependencies, and risks

Stop if:

- Acceptance criteria are not testable.
- Scope is too broad for ticketing.

## Step 3: Design

Read:

- `workflows/prd-to-design.md`
- `roles/product-designer.md`
- `skills/ux-product-design/SKILL.md`
- `templates/DESIGN_BRIEF.template.md`
- `checklists/design-checklist.md`

Output:

- Design brief
- UX flow
- Screen/state list
- Content and accessibility notes

Stop if:

- Critical user flows are missing.
- Design decisions block architecture or backlog creation.

## Step 4: Architecture

Read:

- `workflows/prd-to-architecture.md`
- `roles/architect.md`
- `skills/architecture/SKILL.md`
- `templates/ARCHITECTURE.template.md`
- `checklists/architecture-checklist.md`

Output:

- Technical approach
- Stack-specific constraints
- Data model impact
- API contracts
- Security and privacy considerations
- Test strategy

Stop if:

- Repository, platform, or integration boundaries are unclear.
- Security or data handling risk is unresolved.

## Step 5: Ticket Drafts

Read:

- `workflows/architecture-to-backlog.md`
- `roles/product.md`
- `skills/jira-backlog/SKILL.md`
- `templates/JIRA_EPIC.template.md`
- `templates/JIRA_STORY.template.md`
- `checklists/ticket-ready-checklist.md`

Output:

- Epic draft
- Story/task drafts
- Acceptance criteria
- Dependencies
- Test notes
- Suggested order of execution

Stop if:

- Tickets cannot be developed independently.
- Definition of Ready is not met.

## Step 6: Development Approval

Required approval:

```text
Approval Status = APPROVED_FOR_DEVELOPMENT
```

Before coding, verify:

- PRD exists and passed checklist
- Architecture exists and passed checklist
- Ticket is approved and ordered
- Target repository is known
- Target repository `AGENTS.md` has been read
- Stack deep dive has been read when available

## Step 7: Development

Read:

- `workflows/backlog-to-development.md`
- Correct developer role
- Correct implementation skill
- Correct stack deep dive under `skills/*/stacks/`
- Target repository `AGENTS.md`

Output:

- Code changes in the target product repository
- Tests
- Developer handoff to QA

Stop if:

- Approval is missing.
- Ticket scope is unclear.
- Required test approach cannot be defined.

## Step 8: QA

Read:

- `workflows/development-to-qa.md`
- `roles/qa-developer.md`
- `skills/qa-testing/SKILL.md`
- `checklists/development-handoff-checklist.md`
- `checklists/qa-checklist.md`

Output:

- Test execution summary
- Regression scope
- Defects or sign-off

## Step 9: Release

Read:

- `workflows/qa-to-release.md`
- `roles/devops-release.md`
- `skills/release-management/SKILL.md`
- `templates/RELEASE_PLAN.template.md`
- `checklists/release-checklist.md`

Output:

- Release plan
- Rollback plan
- Monitoring plan
- Release notes

Required approval before execution:

```text
Approval Status = APPROVED_FOR_RELEASE
```

## Step 10: Growth Feedback

Read:

- `workflows/release-to-growth.md`
- `roles/growth-seo.md`
- `roles/data-analytics.md`
- `skills/growth-seo/SKILL.md`
- `skills/data-analytics/SKILL.md`

Output:

- Metrics plan
- Experiment ideas
- SEO/growth follow-ups when relevant

## Expected Final Response Shape

```text
Route used: idea -> discovery -> PRD -> design -> architecture -> backlog
Role used: Product Agent
Skill used: product-discovery, prd-writing
Artifacts produced: PRD draft, ticket drafts
Checklist result: PRD passed with 2 open risks
Approval needed: APPROVED_FOR_DEVELOPMENT before coding
Next step: confirm ticket order or approve Jira creation
```
