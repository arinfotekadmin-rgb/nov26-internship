# 02. Create a Node.js and Express Project

```powershell
mkdir arinfotek-backend
cd arinfotek-backend
npm init -y
npm install express dotenv mysql2 cors
npm install --save-dev nodemon
```

Package roles:
- Express: HTTP server and routes.
- dotenv: reads `.env` configuration.
- mysql2: MySQL client with Promise support.
- cors: browser-origin access policy.
- nodemon: restarts the development server after code changes.

Create `server.js`:

```javascript
const express = require("express");
const app = express();

app.use(express.json());

app.get("/", (req, res) => {
  res.json({ message: "AR INFOTEK API is running" });
});

app.listen(5000, () => {
  console.log("API running at http://localhost:5000");
});
```

Add scripts to `package.json`:

```json
"scripts": {
  "start": "node server.js",
  "dev": "nodemon server.js"
}
```

Run `npm run dev`, then open `http://localhost:5000/`.

**Exercise:** Confirm that the root endpoint returns JSON.
