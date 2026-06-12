# QA to Release

## Purpose
Prepare validated work for controlled release.

## Trigger
QA has produced a release readiness recommendation.

## Required Approval
- Required: `APPROVED_FOR_RELEASE`

## Required Roles
- DevOps Release
- QA Developer
- Product
- Security Reviewer when sensitive scope exists
- Data Analytics when monitoring or metrics are needed

## Required Inputs
- QA results
- Test evidence
- Included tickets
- Known risks
- Rollback risks
- Deployment target
- Approval status

## Steps
1. Read QA results and known risks.
2. Confirm release approval and release scope.
3. Prepare release notes, checklist, rollback plan, and monitoring plan.
4. Validate release gates.
5. Stop if release gates fail.

## Outputs
- Release notes
- Release checklist
- Rollback plan
- Monitoring plan
- Post-release follow-up items

## Artifact Target
- Release plan and release notes.

## Tool Usage
- GitHub release, deployment, or PR tools may be used only when requested and approval exists.
- Do not deploy if release approval or QA evidence is missing.

## Failure Handling
- If QA status is unclear, return to QA.
- If rollback is missing, block release.
- If critical risk is unresolved, block release or require explicit risk acceptance.
