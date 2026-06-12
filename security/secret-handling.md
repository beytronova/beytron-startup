# Secret Handling

Secrets must never be exposed in repositories, tickets, docs, prompts, logs, examples, screenshots, or generated artifacts.

## Secret Examples

- API keys
- OAuth client secrets
- Refresh tokens
- Access tokens
- Private keys
- Signing certificates
- Database URLs with credentials
- Webhook signing secrets
- Payment provider secrets
- Mobile service account files

## Rules

- Do not commit secrets.
- Do not paste secrets into Jira or GitHub issues.
- Do not include secret values in examples.
- Do not log secrets or tokens.
- Do not expose secrets in screenshots.
- Use placeholders such as `<API_KEY>` or `<SECRET_NAME>`.
- Use environment variables or approved secret stores.
- Use least-privilege credentials.
- Rotate secrets after suspected exposure.

## Repository Review

Before release, check:

- `.env` files are ignored or absent.
- Example env files contain placeholders only.
- CI/CD references secret names, not values.
- Logs and tests do not print credentials.
- Mobile config files are reviewed for sensitive content.

## Incident Response

If a secret is exposed:

1. Stop work that depends on the exposed secret.
2. Notify owner.
3. Rotate the secret.
4. Remove the exposure from current artifacts.
5. Assess logs and downstream systems.
6. Document remediation without repeating the secret value.

## Output Format

```text
Secret handling review: PASS|BLOCKED
Secrets found: {none|types only}
Storage method: {env|secret manager|CI secret|unknown}
Rotation needed: {yes|no|unknown}
Blockers: {list}
```
