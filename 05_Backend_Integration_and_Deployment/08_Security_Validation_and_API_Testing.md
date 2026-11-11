# Chapter 8: Security, Validation and API Testing

## 8.1 Validate at both ends
Android validation improves user experience. Backend validation protects the system. The backend must repeat all important validation because clients can be modified.

## 8.2 Backend security checklist
- Validate request bodies and query parameters.
- Authenticate protected routes.
- Authorize each record operation.
- Apply rate limits to login and sensitive endpoints.
- Use parameterised SQL queries.
- Restrict CORS origins for browser clients where applicable.
- Store secrets in server environment variables or a secrets manager.
- Avoid returning stack traces or database errors to clients.
- Record security-relevant events without logging credentials.
- Use HTTPS and maintain dependencies.

## 8.3 API test cases
- Missing token returns 401.
- Valid token for a different student cannot access another student's record.
- Invalid course ID returns a documented error.
- Empty required fields are rejected.
- Duplicate attendance is handled consistently.
- Payment status changes only after backend verification.
- Expired token triggers the expected session flow.

## 8.4 Android test cases
Use fake API implementations for ViewModel unit tests. Use a test backend or controlled mock server for integration tests. Avoid depending on production student data.

## Practical task
Create an API test collection for login, profile, courses, attendance and invoices. Record expected status codes and response examples.
