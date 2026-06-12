# Web Search Integration

## Purpose
Use web search to gather current external evidence for market research, competitor analysis, platform constraints, SEO opportunities, pricing, regulations, documentation, and release/growth planning.

## Required Access
- Internet search access.
- Ability to open source pages when source attribution, current data, or direct verification is required.

## Authentication
No authentication is expected for public web search. If authenticated sources are required, use only approved connectors and record the source type.

## Inputs
- Research question
- Target audience or market
- Geography/language when relevant
- Time sensitivity
- Source type preference
- Workflow stage

## Outputs
- Source links
- Evidence summary
- Fact vs assumption separation
- Confidence level
- Date-sensitive notes
- Open questions
- Recommendation or implication

## Workflow Usage

Allowed workflows:

- `workflows/idea-to-discovery.md`
- `workflows/discovery-to-prd.md` when current evidence affects scope
- `workflows/release-to-growth.md`

Use web search when information is current, uncertain, external, market-dependent, platform-dependent, or high-stakes.

## Source Standards
- Prefer primary sources for technical, legal, platform, or pricing claims.
- Prefer recent sources for market, competitor, SEO, and product claims.
- Record dates when the information may change.
- Do not overquote sources.
- Separate facts from interpretation.

## Failure Handling
- If sources conflict, show the conflict and confidence level.
- If current evidence is unavailable, mark assumption and propose validation.
- If source credibility is weak, do not treat it as fact.
- If the research result changes scope materially, route back to Product before PRD/backlog.
