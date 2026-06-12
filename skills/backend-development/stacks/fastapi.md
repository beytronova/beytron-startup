# FastAPI Stack Deep Dive

Use this when a target backend repository is a FastAPI service.

## Stack Signals
- `fastapi` dependency exists.
- Application uses `FastAPI()` app instance.
- Routes use decorators such as `@router.get` or `@app.post`.

## Primary Language
- Python.

## File Structure Rules
- Keep routers focused on HTTP boundary behavior.
- Keep business logic in services/use cases.
- Keep persistence in repositories/models/data modules.
- Use Pydantic models for request/response schemas.
- Keep dependencies/auth in dependency functions or established patterns.
- Keep migrations in Alembic or existing migration system.

## Architecture Rules
- Use typed request and response models.
- Validate inputs at API boundaries.
- Keep auth/authz explicit with dependencies or middleware.
- Use transactions for multi-step writes.
- Keep external integrations behind client/adaptor modules.
- Include structured logging or repository-native logging.

## Testing
Common checks:

```bash
pytest
python -m pytest
ruff check .
ruff format --check .
mypy .
alembic upgrade head
```

## Do Not Do
- Do not put business logic directly in route handlers.
- Do not return raw internal models when response models are expected.
- Do not skip migration notes for schema changes.
- Do not log secrets or sensitive payloads.

## Output Notes
When using this stack, report:

- Routers/services/models changed
- Pydantic schema changes
- Auth/authz impact
- Migration impact
- Tests/checks run
