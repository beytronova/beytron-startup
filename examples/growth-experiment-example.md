# Growth Experiment Golden Path

Use this example after a feature is released or when the user asks for growth, SEO, activation, retention, or measurement work.

## Example User Prompt

```text
The subscription prediction feature is released. Create a growth and measurement plan for the next iteration.
```

## Route

- Stage: growth
- Workflow: `workflows/release-to-growth.md`
- Primary roles: Growth SEO, Data Analytics
- Supporting roles: Product, Product Designer, Developer when instrumentation is needed
- Primary skills: `skills/growth-seo/SKILL.md`, `skills/data-analytics/SKILL.md`

## Required Inputs

- Release summary
- PRD goals and success metrics
- Analytics events currently available
- Target users or segments
- Funnel or lifecycle stage
- Known constraints

## Step 1: Read Growth Context

Read:

- `workflows/release-to-growth.md`
- `roles/growth-seo.md`
- `roles/data-analytics.md`
- `skills/growth-seo/SKILL.md`
- `skills/data-analytics/SKILL.md`
- `templates/GROWTH_PLAN.template.md`
- `templates/METRICS_PLAN.template.md`

## Step 2: Define Measurement Plan

Capture:

- North-star or feature success metric
- Supporting metrics
- Event names and properties
- Funnel steps
- Segment definitions
- Baseline needed
- Decision threshold

Stop if metrics cannot be measured with existing or planned instrumentation.

## Step 3: Define Experiment

Include:

- Hypothesis
- Target audience
- Variant or intervention
- Expected impact
- Guardrail metrics
- Duration
- Rollout criteria
- Stop criteria

## Step 4: Identify Implementation Needs

If code changes are required, produce ticket drafts instead of coding directly.

Ticket drafts may include:

- Analytics event instrumentation
- Landing page SEO updates
- In-app onboarding change
- Email/push campaign integration
- Dashboard/report creation

Development still requires:

```text
Approval Status = APPROVED_FOR_DEVELOPMENT
```

## Step 5: Output Growth Plan

Use:

- `templates/GROWTH_PLAN.template.md`
- `templates/METRICS_PLAN.template.md`

Output:

- Growth goal
- Target segment
- Experiment hypothesis
- Events and metrics
- Required tickets
- Risks
- Approval needed

## Expected Final Response Shape

```text
Growth stage: release-to-growth
Feature: subscription prediction
Primary metric: weekly active users using prediction insight
Experiment: onboarding card explaining upcoming subscription risk
Instrumentation needed: prediction_card_viewed, prediction_card_action_clicked
Tickets drafted: analytics instrumentation, onboarding card variant
Approval needed: APPROVED_FOR_DEVELOPMENT before implementation
```
