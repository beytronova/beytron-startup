# Product Discovery Skill

Use when turning a raw idea, stakeholder request, or market signal into a validated product opportunity.

## Triggers
- User proposes a new product or feature idea.
- Discovery, research, validation, competitor review, or opportunity framing is requested.
- A PRD is being considered but the problem or audience is not yet clear.

## Artifact Structure
- Idea name and slug
- Raw idea
- Target user
- Problem statement
- Current alternatives
- Evidence
- Assumptions
- Risks
- Open questions
- Recommendation
- Next approval state

## Research Data Model
Track facts separately from assumptions:

```text
Fact:
Source:
Confidence: High / Medium / Low
Implication:
```

Track assumptions explicitly:

```text
Assumption:
Validation method:
Risk if false:
```

## Integration Standards
- Use web search for current market, competitor, regulatory, platform, or pricing evidence when relevant.
- Use Jira only after backlog approval.
- Use GitHub only to read existing project context or write approved documentation.
- Do not create product code or repositories during discovery.

## Required Reading
- `roles/product.md`
- `workflows/idea-to-discovery.md`
- `templates/PRD.template.md` only after discovery is complete
- `governance/approval-rules.md`

## Protocol
1. Capture the raw idea without rewriting its intent.
2. Clarify problem, target user, current alternatives, constraints, and expected outcome.
3. Separate facts, assumptions, unknowns, and risks.
4. Research market, competitors, user pain, technical feasibility, and monetization signals when tools are available.
5. Decide whether the idea should continue to PRD, needs more research, or should stop.
6. Do not write product code.

## Output Format
- Summary
- Target user
- Problem statement
- Evidence table
- Assumptions table
- Risks
- Open questions
- Continue/stop recommendation
- Required next approval state

## Stop Conditions
- Target user is unknown.
- Problem is too vague to evaluate.
- Approval state prevents discovery.

## Example Prompts
```text
Use Product Discovery to research this idea and produce a continue/stop recommendation with assumptions and open questions.
```
