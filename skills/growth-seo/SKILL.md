# Growth SEO Skill

Use when planning launch, SEO, content, positioning, and measurable growth experiments.

## Triggers
- User asks for SEO, launch plan, content strategy, positioning, or growth experiments.
- A release is ready for market-facing planning.
- Product goals need acquisition or activation experiments.

## Artifact Structure
Use `templates/GROWTH_PLAN.template.md` and include:
- Audience
- Positioning
- SEO/content opportunities
- Launch channels
- Experiments
- Metrics
- Follow-up

## SEO and Experiment Data Model
SEO opportunity:

```text
Intent:
Keyword/topic:
Funnel stage:
Content asset:
User problem:
Priority:
Measurement:
```

Experiment:

```text
Hypothesis:
Audience:
Change:
Primary metric:
Guardrail metric:
Duration:
Decision rule:
Owner:
```

## Integration Standards
- Coordinate measurement with `templates/METRICS_PLAN.template.md`.
- Do not propose tracking that violates privacy/security rules.
- Route web content changes to Web Development.
- Route event tracking changes to Web, Mobile, Backend, or Data Analytics based on implementation ownership.
- Keep messaging aligned with PRD and release notes.

## Required Reading
- `roles/growth-seo.md`
- `roles/data-analytics.md`
- `workflows/release-to-growth.md`
- `templates/GROWTH_PLAN.template.md`
- `templates/METRICS_PLAN.template.md`

## Protocol
1. Read product positioning, target audience, release scope, and metrics.
2. Map audience journey, search intent, competitors, alternatives, and content gaps.
3. Define launch messaging that does not overpromise beyond product truth.
4. Create measurable experiments with hypothesis, target metric, owner, duration, and decision rule.
5. Coordinate analytics needs before launch.
6. Produce follow-up learning loop.

## Output Format
- Audience and intent map
- Positioning
- SEO/content opportunities
- Launch channels
- Experiments
- Metrics and analytics needs
- Follow-up plan

## Stop Conditions
- Target audience is unclear.
- Launch scope is undefined.
- Metrics cannot be measured.
- Messaging would misrepresent the product.

## Example Prompts
```text
Use Growth SEO to create a launch, SEO, content, and experiment plan for this release.
```
