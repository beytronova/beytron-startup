# Android Networking Deep Dive

Use this when Android work touches REST, GraphQL, Retrofit, Ktor, OkHttp, auth headers, token refresh, interceptors, retries, offline cache, or API error handling.

## Stack Signals

- Dependencies include Retrofit, OkHttp, Ktor, Apollo, Moshi, Gson, Kotlin serialization, or GraphQL clients.
- Code uses API services, interceptors, DTOs, mappers, or repository network calls.

## Primary Language

- Kotlin.

## Architecture Rules

- Keep network calls behind repositories or data sources.
- Keep DTOs separate from domain/UI models when complexity warrants it.
- Map API errors into domain errors.
- Keep auth/session concerns in a dedicated auth layer or interceptor.
- Avoid calling APIs directly from UI.

## Auth and Token Rules

- Do not log tokens.
- Keep token refresh behavior centralized.
- Handle expired sessions explicitly.
- Avoid infinite retry loops.
- Protect refresh token storage.

## Error Handling

- Handle network unavailable, timeout, server error, validation error, auth error, and parsing error.
- Provide user-appropriate messages through UI state.
- Preserve diagnostic details without exposing sensitive data.

## Retry and Timeout Rules

- Use bounded retries only when product/architecture allows it.
- Avoid retrying non-idempotent requests blindly.
- Keep timeouts intentional.
- Respect offline and metered-network behavior when relevant.

## Serialization Rules

- Keep request/response schemas explicit.
- Handle nullable and optional fields safely.
- Avoid broad `Any` or loosely typed maps unless required by API shape.

## Testing

Common checks:

```bash
./gradlew test
./gradlew lint
```

Recommended tests:

- Repository tests with fake API.
- MockWebServer tests when repository uses OkHttp/Retrofit.
- Error mapping tests.
- Token refresh tests.

## Do Not Do

- Do not call network clients directly from UI.
- Do not log request bodies containing sensitive data.
- Do not add interceptors that leak credentials.
- Do not ignore API error bodies when acceptance criteria depend on them.

## Output Notes

When using this stack, report:

- API clients/endpoints changed
- DTO/domain mapping impact
- Auth/token impact
- Error/retry behavior
- Tests/checks run
