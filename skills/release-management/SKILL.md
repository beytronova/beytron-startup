# Release Management Skill

Use when preparing approved, tested work for release.

## Triggers
- User asks for release plan, release notes, deployment, rollback, or monitoring.
- QA recommends release readiness.
- `APPROVED_FOR_RELEASE` is present.

## Supported Release Systems
- GitHub Actions, GitLab CI, CircleCI, Bitrise, Fastlane, Vercel, Netlify, Docker, Kubernetes, or repository-native deployment
- Mobile release: TestFlight, App Store Connect, Google Play Console, internal tracks
- Web/backend release: preview, staging, production, canary, blue/green, rolling, or manual deployment

## Release Artifact Rules
- Release notes must map to included tickets.
- Deployment steps must name environment, command/tool, owner, and expected result.
- Rollback plan must include trigger, owner, steps, and data/migration considerations.
- Migration plan must include forward and rollback strategy when possible.
- Monitoring must include metrics/logs/dashboard, alert owner, and review window.

## Environment Rules
- Confirm required env vars, secrets, feature flags, domains, certificates, and third-party keys.
- Do not expose secret values in release notes.
- Verify staging/production differences before release.
- Document config changes and responsible owner.

## Common Commands
Use repository-native commands first. Examples:

```bash
npm run build
npm run test
pnpm build
pnpm test
docker build .
docker compose up
kubectl rollout status deployment/name
kubectl rollout undo deployment/name
fastlane beta
fastlane release
flutter build apk
flutter build ios --release
```

## Required Reading
- `roles/devops-release.md`
- `workflows/qa-to-release.md`
- `handoffs/qa-to-release.md`
- `templates/RELEASE_PLAN.template.md`
- `governance/release-gates.md`

## Protocol
1. Confirm release approval and scope.
2. Review QA status, blockers, known risks, migrations, environment config, and dependencies.
3. Prepare release notes, deployment steps, rollback plan, and monitoring plan.
4. Stop if any release gate fails.
5. After release, record release outcome, incidents, and follow-up work.

## Output Format
- Release scope
- Included tickets
- QA status
- Environment/config status
- Known risks
- Deployment steps
- Rollback plan
- Migration impact
- Monitoring plan
- Approval status

## Stop Conditions
- Release approval is missing.
- QA status is unclear.
- Rollback plan is missing.
- Critical risk is unresolved.
- Required environment or secret configuration is unknown.

## Example Prompts
```text
Use Release Management to prepare release notes, deployment checklist, rollback plan, env checks, migration notes, and monitoring plan.
```
