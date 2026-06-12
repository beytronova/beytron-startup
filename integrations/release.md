# Release Integration

## Purpose
Use release systems to prepare, deploy, verify, monitor, and roll back approved releases across web, backend, mobile, and infrastructure targets.

## Required Access
- Read access to CI/CD status, builds, deployments, and release artifacts.
- Write/deploy access only when `APPROVED_FOR_RELEASE` exists and the user explicitly requests release execution.
- Access to monitoring dashboards or logs when release verification requires it.

## Authentication
Release access must come from approved CI/CD, hosting, store, or infrastructure credentials.

Before release actions, verify:

- `APPROVED_FOR_RELEASE`
- Release owner
- Target environment
- Included tickets
- QA evidence
- Rollback plan
- Environment and secret readiness

## Inputs
- Release scope
- Included tickets
- QA status and evidence
- Known risks
- Environment target
- Deployment steps
- Rollback plan
- Monitoring plan
- Approval status

## Outputs
- Release/deployment reference
- Release notes
- Deployment log or summary
- Verification result
- Monitoring plan/status
- Rollback status when used
- Follow-up items

## Workflow Usage

Allowed workflow:

- `workflows/qa-to-release.md`

Release execution is not allowed from discovery, PRD, design, architecture, backlog, development, or QA workflows.

## Release System Examples
- GitHub Actions
- GitLab CI
- CircleCI
- Bitrise
- Fastlane
- Vercel
- Netlify
- Docker/Kubernetes
- TestFlight
- App Store Connect
- Google Play Console

## Failure Handling
- If approval is missing, stop.
- If QA evidence is missing, route back to QA.
- If rollback plan is missing, block release.
- If deployment fails, record failure, logs, impact, and rollback recommendation.
- If monitoring is unavailable, mark release conditional or blocked depending on risk.
- If secrets or environment values are missing, stop without exposing secret values.
