# 09. Validation, Authentication and Security

## Validate requests
The sample checks required fields and IDs. For a production app, consider Zod, Joi or express-validator. Validate data type, length, format and allowed values on the server.

## Prevent SQL injection
Safe:

```javascript
const [rows] = await pool.execute(
  "SELECT * FROM students WHERE email = ?",
  [email]
);
```

Unsafe:

```javascript
// Never concatenate user input into SQL.
const sql = "SELECT * FROM students WHERE email = '" + email + "'";
```

## Password storage
Never store plain-text passwords. Use a password hashing library such as bcrypt or Argon2. Do not use reversible encryption as a password storage method.

## Authentication flow
1. Client sends credentials over HTTPS.
2. Backend verifies the password hash.
3. Backend issues a session or access token.
4. Client sends the credential on protected requests.
5. Backend checks identity and permissions for every protected operation.

Authentication answers who the user is. Authorization checks what that user can access.

## Production checklist
- HTTPS.
- Dedicated MySQL account with minimum privileges.
- `.env` excluded from Git.
- Secrets stored securely.
- Parameterised SQL.
- Input validation.
- Rate limiting for login and sensitive routes.
- Correct CORS allowlist for browser clients.
- Record-level authorization.
- Safe error messages.
- Database backups and tested restoration.

The sample CRUD API has no authentication. Do not expose real student records until authentication and authorization are implemented.
