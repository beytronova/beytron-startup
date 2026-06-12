# Data Analytics Skill

Use when defining product metrics, analytics events, dashboards, experiment measurements, and post-release learning loops.

## Triggers
- User asks for metrics, analytics, dashboards, event tracking, experiments, or measurement plans.
- PRD needs measurable success criteria.
- Growth, release, or product decisions need observable signals.
- Workflow reaches `release-to-growth` or analytics support is requested in PRD/design/architecture.

## Supported Analytics Domains
- Product success metrics
- Funnel and activation metrics
- Retention, revenue, referral, and engagement metrics
- Event tracking plans
- Experiment measurement
- Release monitoring
- Dashboard requirements
- Data quality and privacy review

## Required Inputs
- PRD goals or release goals
- User flows
- Target audience or segment
- Existing analytics stack when available
- Privacy/security constraints
- Experiment hypotheses when relevant

## Required Reading
- `roles/data-analytics.md`
- `templates/METRICS_PLAN.template.md`
- `workflows/release-to-growth.md`
- `governance/security-standards.md`
- `governance/release-gates.md`

## Protocol
1. Map product goals to measurable metrics.
2. Define event names, triggers, properties, user identity model, and privacy notes.
3. Identify dashboard needs, review cadence, and decision owners.
4. Define experiment metrics, guardrails, duration, and decision rules.
5. Document data quality, consent, retention, access, and instrumentation risks.
6. Route implementation changes to the correct development role.

## Metric Model
Use this format:

```text
Metric:
Definition:
Why it matters:
Baseline:
Target:
Window:
Segment:
Source:
Owner:
Decision supported:
```

## Event Model
Use this format:

```text
Event name:
Trigger:
Actor:
Object:
Required properties:
Optional properties:
Identity behavior:
Privacy notes:
Implementation owner:
Validation method:
```

## Output Format
- Metrics plan
- Event tracking plan
- Dashboard requirements
- Experiment measurement plan
- Privacy notes
- Data quality risks
- Implementation ownership

## Quality Gates
- Metrics map to product goals.
- Events have clear triggers and properties.
- Privacy impact is documented.
- Dashboard/review path is defined.
- Experiment decision rules are measurable.

## Stop Conditions
- Metric is not observable.
- Identity model is unclear.
- Data collection conflicts with privacy/security requirements.
- Event ownership is unknown.
- Required analytics stack is unavailable or undefined.

## Example Prompts
```text
Use Data Analytics to define success metrics, tracking events, dashboards, and experiment measurement for this PRD.
```
