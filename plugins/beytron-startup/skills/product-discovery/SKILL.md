---
name: product-discovery
description: Run Beytron product discovery from raw idea to validated problem, target user, assumptions, research needs, success metrics, and approval-ready next steps.
---

# Product Discovery

Use this skill when a raw idea, vague product request, incubator item, or stakeholder note must become structured discovery output before PRD, design, architecture, Jira, repository creation, or code.

## Purpose

Product Discovery protects the system from jumping into implementation too early. It turns ambiguous ideas into clear product context, risk, user value, and approval-ready artifacts.

## Role Alignment

Primary role: `product`

Supporting roles:

- `data_analytics` for metrics and evidence.
- `growth_seo` for acquisition hypotheses.
- `architect` for early feasibility risk only.

## Required Inputs

- Raw idea, stakeholder request, or existing idea artifact.
- Current approval status.
- Target user or suspected user segment.
- Known business goal, constraint, or market signal.
- Existing research, if available.

## Workflow Rules

- If the idea has no product repository, keep work in the incubator or planning workspace.
- Do not create product code.
- Do not create a product repository.
- Do not create Jira tickets unless approval permits Jira creation.
- Capture unknowns explicitly instead of inventing certainty.
- Separate user problem, business goal, assumptions, and solution ideas.

## Artifact Outputs

- IDEA summary.
- RESEARCH direction or research summary.
- Problem statement.
- Target user definition.
- Assumption list.
- MVP hypothesis.
- Success metric candidates.
- Approval recommendation.

## Quality Bar

Discovery is ready for PRD only when the problem, target user, value proposition, assumptions, non-goals, risks, and measurable outcome are clear enough for a product owner to review.

## Stop Conditions

- Approval status is unknown or `REJECTED`.
- The user requests implementation before PRD and architecture are approved.
- Target user or problem is too vague to create a responsible PRD.
