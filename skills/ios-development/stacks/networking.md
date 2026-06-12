# iOS Networking Deep Dive

Use this when iOS work touches URLSession, API clients, GraphQL, auth headers, token refresh, retries, decoding, offline cache, or API error handling.

## Stack Signals

- Code uses `URLSession`, custom API clients, GraphQL clients, request builders, decoders, mappers, auth interceptors, or networking services.
- Feature requires remote API integration.

## Primary Language

- Swift.

## Architecture Rules

- Keep network calls behind services, repositories, or API clients.
- Keep DTOs separate from domain/UI models when complexity warrants it.
- Map API errors into domain errors.
- Keep auth/session concerns centralized.
- Avoid calling APIs directly from Views or ViewControllers.

## Auth and Token Rules

- Do not log tokens.
- Keep token refresh behavior centralized.
- Handle expired sessions explicitly.
- Avoid infinite retry loops.
- Store refresh tokens securely.

## Error Handling

- Handle offline, timeout, server error, validation error, auth error, and decoding error.
- Provide user-appropriate messages through UI state.
- Preserve diagnostic details without exposing sensitive data.

## Retry and Timeout Rules

- Use bounded retries only when product/architecture allows it.
- Avoid retrying non-idempotent requests blindly.
- Keep timeouts intentional.
- Respect offline and constrained network behavior when relevant.

## Decoding Rules

- Keep request/response schemas explicit.
- Handle optional fields safely.
- Avoid force unwraps for decoded values.
- Validate date, number, and locale-sensitive decoding.

## Testing

Common checks:

```bash
xcodebuild -scheme App -destination 'platform=iOS Simulator,name=iPhone 16' test
swift test
```

Recommended tests:

- API client tests with mocked URLProtocol or repository convention.
- Error mapping tests.
- Token refresh tests.
- Decoding tests with fixtures.

## Do Not Do

- Do not call network clients directly from UI.
- Do not log request/response bodies containing sensitive data.
- Do not ignore status codes and API error bodies.
- Do not store tokens outside secure storage.

## Output Notes

When using this stack, report:

- API clients/endpoints changed
- DTO/domain mapping impact
- Auth/token impact
- Error/retry behavior
- Tests/checks run
