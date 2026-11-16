# 06. Connect Express to MySQL using mysql2

The Promise API from `mysql2` works with `async` and `await`. Use a connection pool so requests can reuse database connections.

Create `src/config/db.js`:

```javascript
const mysql = require("mysql2/promise");

const pool = mysql.createPool({
  host: process.env.DB_HOST,
  port: Number(process.env.DB_PORT || 3306),
  user: process.env.DB_USER,
  password: process.env.DB_PASSWORD,
  database: process.env.DB_NAME,
  waitForConnections: true,
  connectionLimit: 10,
  queueLimit: 0
});

module.exports = pool;
```

Update `src/server.js`:

```javascript
require("dotenv").config();

const app = require("./app");
const pool = require("./config/db");

const PORT = process.env.PORT || 5000;

async function startServer() {
  try {
    const connection = await pool.getConnection();
    await connection.ping();
    connection.release();

    console.log("MySQL connection successful");

    app.listen(PORT, () => {
      console.log(`API listening on port ${PORT}`);
    });
  } catch (error) {
    console.error("Unable to connect to MySQL:", error.message);
    process.exit(1);
  }
}

startServer();
```

## Common errors

| Error | What to check |
|---|---|
| ECONNREFUSED | MySQL service and port |
| ER_ACCESS_DENIED_ERROR | Username, password and grants |
| ER_BAD_DB_ERROR | Database name |
| ETIMEDOUT | Host, firewall and network |
| Unknown database | Database spelling and existence |

**Exercise:** Start the API and verify the success message.
