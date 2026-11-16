# AR INFOTEK: Node.js Backend with Express, dotenv and MySQL

A self-learning course for Windows 10/11 and VS Code. It covers installation, Express setup, environment variables, MySQL, `mysql2`, REST APIs, testing, security and client integration.

## Learning sequence
1. Install Node.js, VS Code and MySQL.
2. Create an Express project.
3. Configure dotenv and project structure.
4. Create MySQL database and tables.
5. Connect using mysql2 connection pooling.
6. Build CRUD APIs.
7. Test with Postman.
8. Add validation and security.
9. Connect React or Android.
10. Complete the Student Management API project.

## Architecture

```text
React / Android client
        | HTTP + JSON
        v
   Node.js + Express
        | mysql2
        v
       MySQL
```

Never put MySQL credentials in browser code or an Android app. Database access belongs on the backend.

The course uses CommonJS (`require`/`module.exports`) for consistency. Use a currently supported Node.js LTS release and current compatible package versions.
