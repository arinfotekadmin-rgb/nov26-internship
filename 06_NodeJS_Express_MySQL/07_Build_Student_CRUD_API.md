# 07. Build a Student CRUD REST API

CRUD means Create, Read, Update and Delete.

Create `src/controllers/studentController.js`:

```javascript
const pool = require("../config/db");

async function getStudents(req, res, next) {
  try {
    const [rows] = await pool.execute(
      `SELECT student_id, full_name, email, phone, created_at
       FROM students ORDER BY student_id DESC`
    );
    res.json({ data: rows });
  } catch (error) {
    next(error);
  }
}

async function getStudentById(req, res, next) {
  try {
    const id = Number(req.params.id);
    if (!Number.isInteger(id) || id <= 0) {
      return res.status(400).json({ message: "Invalid student ID" });
    }

    const [rows] = await pool.execute(
      `SELECT student_id, full_name, email, phone, created_at
       FROM students WHERE student_id = ?`,
      [id]
    );

    if (rows.length === 0) {
      return res.status(404).json({ message: "Student not found" });
    }
    res.json({ data: rows[0] });
  } catch (error) {
    next(error);
  }
}

async function createStudent(req, res, next) {
  try {
    const { full_name, email, phone } = req.body;

    if (
      typeof full_name !== "string" || !full_name.trim() ||
      typeof email !== "string" || !email.trim()
    ) {
      return res.status(400).json({
        message: "Full name and email are required"
      });
    }

    const [result] = await pool.execute(
      `INSERT INTO students (full_name, email, phone)
       VALUES (?, ?, ?)`,
      [full_name.trim(), email.trim().toLowerCase(), phone || null]
    );

    res.status(201).json({
      message: "Student created",
      student_id: result.insertId
    });
  } catch (error) {
    if (error.code === "ER_DUP_ENTRY") {
      return res.status(409).json({ message: "Email already exists" });
    }
    next(error);
  }
}

async function updateStudent(req, res, next) {
  try {
    const id = Number(req.params.id);
    const { full_name, email, phone } = req.body;

    if (!Number.isInteger(id) || id <= 0) {
      return res.status(400).json({ message: "Invalid student ID" });
    }
    if (
      typeof full_name !== "string" || !full_name.trim() ||
      typeof email !== "string" || !email.trim()
    ) {
      return res.status(400).json({
        message: "Full name and email are required"
      });
    }

    const [result] = await pool.execute(
      `UPDATE students
       SET full_name = ?, email = ?, phone = ?
       WHERE student_id = ?`,
      [full_name.trim(), email.trim().toLowerCase(), phone || null, id]
    );

    if (result.affectedRows === 0) {
      return res.status(404).json({ message: "Student not found" });
    }
    res.json({ message: "Student updated" });
  } catch (error) {
    if (error.code === "ER_DUP_ENTRY") {
      return res.status(409).json({ message: "Email already exists" });
    }
    next(error);
  }
}

async function deleteStudent(req, res, next) {
  try {
    const id = Number(req.params.id);
    if (!Number.isInteger(id) || id <= 0) {
      return res.status(400).json({ message: "Invalid student ID" });
    }

    const [result] = await pool.execute(
      "DELETE FROM students WHERE student_id = ?",
      [id]
    );

    if (result.affectedRows === 0) {
      return res.status(404).json({ message: "Student not found" });
    }
    res.json({ message: "Student deleted" });
  } catch (error) {
    next(error);
  }
}

module.exports = {
  getStudents,
  getStudentById,
  createStudent,
  updateStudent,
  deleteStudent
};
```

Create `src/routes/studentRoutes.js`:

```javascript
const express = require("express");
const controller = require("../controllers/studentController");

const router = express.Router();

router.get("/", controller.getStudents);
router.get("/:id", controller.getStudentById);
router.post("/", controller.createStudent);
router.put("/:id", controller.updateStudent);
router.delete("/:id", controller.deleteStudent);

module.exports = router;
```

Register routes in `src/app.js`:

```javascript
const express = require("express");
const cors = require("cors");
const studentRoutes = require("./routes/studentRoutes");
const errorHandler = require("./middleware/errorHandler");

const app = express();
app.use(cors());
app.use(express.json());

app.get("/", (req, res) => {
  res.json({ message: "AR INFOTEK API is running" });
});

app.use("/api/students", studentRoutes);
app.use(errorHandler);

module.exports = app;
```

Create `src/middleware/errorHandler.js`:

```javascript
function errorHandler(error, req, res, next) {
  console.error(error);
  res.status(500).json({ message: "Internal server error" });
}

module.exports = errorHandler;
```

## Endpoint summary

| Method | Endpoint | Purpose |
|---|---|---|
| GET | `/api/students` | List students |
| GET | `/api/students/1` | Read student |
| POST | `/api/students` | Create student |
| PUT | `/api/students/1` | Update student |
| DELETE | `/api/students/1` | Delete student |

The SQL uses `?` placeholders. Never concatenate user input into SQL statements.
