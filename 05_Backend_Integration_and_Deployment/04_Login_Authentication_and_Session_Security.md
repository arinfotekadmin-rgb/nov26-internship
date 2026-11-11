# Chapter 4: Login, Authentication and Session Security

## 4.1 Login flow
1. User enters credentials.
2. Android validates basic input format.
3. Android sends credentials to the HTTPS login endpoint.
4. Express validates credentials against the database.
5. Backend returns a session token or another documented authentication mechanism.
6. Android stores the token using an appropriate secure storage approach.
7. Android sends the token with protected API requests.
8. Backend validates the token and authorizes each operation.

## 4.2 Bearer token example
If the backend uses bearer tokens, the request header commonly looks like:

```http
Authorization: Bearer <access-token>
```

Use an OkHttp interceptor to add the token. The token must come from your session manager, not from a hard-coded string.

## 4.3 Security requirements
- Use HTTPS in production.
- Never store passwords after login.
- Never hard-code tokens, API secrets or database credentials.
- Do not print tokens in Logcat.
- Expire and revoke sessions on the backend.
- Handle 401 responses and send the user through the login flow.
- Enforce role and record ownership checks on the backend.
- Use short-lived access tokens and a carefully designed refresh mechanism if needed.

Android Keystore can protect cryptographic keys. It does not automatically make arbitrary application data secure. Select a maintained secure-storage approach and review its current security guidance.

## 4.4 Logout
Logout should clear local session state and call a backend revocation endpoint if the backend supports it. Clear user-specific cached data when appropriate.

## Practical task
Implement login, authenticated profile retrieval and logout against a test backend. Verify that a user cannot retrieve another student's profile by changing an ID.
