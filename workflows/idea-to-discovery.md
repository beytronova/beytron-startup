# Idea to Discovery

## Purpose
Turn a raw idea into a researched opportunity before PRD, backlog, repository creation, or code.

## Trigger
A stakeholder proposes a new product, feature, improvement, or market opportunity.

## Required Approval
- Minimum: `APPROVED_FOR_DISCOVERY`
- If status is `WAITING`, only clarify missing information.
- If status is `REJECTED`, stop.

## Required Roles
- Product
- Growth SEO when market/search demand matters
- Data Analytics when success metrics are unclear
- Security Reviewer when sensitive data is implied

## Required Inputs
- Raw idea
- Target audience if known
- Business constraint if known
- Approval status

## Steps
1. Capture the idea exactly enough to preserve stakeholder intent.
2. Clarify user, problem, alternatives, assumptions, and constraints.
3. Research evidence, risks, market signals, competitors, and feasibility.
4. Separate facts from assumptions.
5. Produce continue, revise, research-more, or stop recommendation.

## Outputs
- Discovery summary
- Evidence and assumptions
- Open questions
- Risks
- Continue/stop recommendation
- Next approval request

## Artifact Target
- Discovery artifact in the active project docs or idea workspace.
- If no product repository exists, use the incubator or idea workspace defined by the parent system.

## Tool Usage
- Web/search tools may be used when live market evidence is needed.
- Do not create Jira issues, GitHub repos, branches, PRs, or code in this workflow.

## Failure Handling
- If evidence is weak, produce a research-more recommendation.
- If user/problem is unclear, stop and ask for clarification.
- If approval is missing, produce only a clarification summary.
