# Chapter 7: Error Handling, Logging and Diagnostics

## 7.1 Handle expected failures
Common failures include:
- No network connection
- API timeout
- Invalid response data
- Expired login session
- Local database failure
- Permission denial

Show users a useful message and a clear next action. Avoid exposing stack traces or internal server details.

## 7.2 Logging
Use Android Log for development diagnostics. Do not log passwords, access tokens, personal student data, payment details or full API request bodies containing sensitive data.

```kotlin
Log.d("CoursesViewModel", "Loading courses")
Log.e("CoursesViewModel", "Course request failed", exception)
```

Remove verbose diagnostic logs from production builds or restrict them appropriately.

## 7.3 Network timeouts
Configure connection and read timeouts in the networking client. Treat timeout as a recoverable error when appropriate. Provide Retry without creating duplicate submissions.

## 7.4 Diagnostics checklist
- Reproduce the issue.
- Read Logcat around the failure timestamp.
- Identify whether the failure is in UI, local storage or network.
- Record the HTTP status code where applicable.
- Fix the cause and add a regression test.

## Practical task
Simulate offline mode and an API error. Display a friendly error state and a Retry action.

## Check your understanding
1. What information should never appear in logs?
2. How should an app respond to a timeout?
3. What is a regression test?
