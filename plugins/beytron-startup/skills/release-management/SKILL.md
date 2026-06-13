---
name: release-management
description: Manage release readiness with CI/CD, environments, migrations, versioning, rollback, monitoring, release notes, approvals, and post-release checks.
---

# Release Management

Use this skill when work is preparing for staging, production, app store release, rollout, rollback, or release approval.

## Required Inputs

- Release scope.
- QA evidence.
- Migration and dependency notes.
- Monitoring and rollback plan.
- Approval status.

## Rules

- Do not release without approval.
- Treat migrations as high risk.
- Include rollback and monitoring before production release.
- Ensure release notes match shipped scope.
- Verify environment variables and secrets without exposing values.

## Outputs

- Release plan.
- Rollback plan.
- Deployment checklist.
- Monitoring plan.
- Release notes.
- Post-release validation plan.
