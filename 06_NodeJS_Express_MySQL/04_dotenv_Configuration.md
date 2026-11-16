# 04. Environment Variables with dotenv

Create `.env` in the project root:

```env
PORT=5000
DB_HOST=localhost
DB_PORT=3306
DB_USER=arinfotek_app
DB_PASSWORD=replace_with_a_strong_password
DB_NAME=arinfotek_db
```

Load dotenv before reading configuration:

```javascript
require("dotenv").config();

const PORT = process.env.PORT || 5000;
```

Never print passwords or tokens in terminal logs.

Create `.gitignore`:

```gitignore
node_modules/
.env
.env.*
!.env.example
npm-debug.log*
```

Create `.env.example` with placeholder values only. Commit `.env.example`, never `.env`.

Validate required values at startup:

```javascript
const required = ["DB_HOST", "DB_USER", "DB_PASSWORD", "DB_NAME"];

for (const key of required) {
  if (!process.env[key]) {
    throw new Error(`Missing environment variable: ${key}`);
  }
}
```

**Exercise:** Change `PORT` in `.env` and verify that the server uses the new port.
