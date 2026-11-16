# 03. Project Structure and Modules

Create this structure:

```text
arinfotek-backend/
  src/
    config/db.js
    controllers/studentController.js
    routes/studentRoutes.js
    middleware/errorHandler.js
    app.js
    server.js
  .env
  .env.example
  .gitignore
  package.json
```

Use CommonJS consistently:

```javascript
const express = require("express");
module.exports = router;
```

Create `src/app.js`:

```javascript
const express = require("express");
const cors = require("cors");

const app = express();
app.use(cors());
app.use(express.json());

app.get("/", (req, res) => {
  res.json({ message: "AR INFOTEK Backend API" });
});

module.exports = app;
```

Create `src/server.js`:

```javascript
require("dotenv").config();
const app = require("./app");

const PORT = process.env.PORT || 5000;

app.listen(PORT, () => {
  console.log(`API listening on port ${PORT}`);
});
```

For production, configure CORS with the exact browser frontend origins you trust. CORS is not authentication.

**Exercise:** Move your initial route into `app.js` and run the app through `src/server.js`.
