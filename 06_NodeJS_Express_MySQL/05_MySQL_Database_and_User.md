# 05. Create MySQL Database, User and Tables

Do not use the MySQL root account in your application. Create a dedicated account with limited privileges.

```sql
CREATE DATABASE arinfotek_db
  CHARACTER SET utf8mb4
  COLLATE utf8mb4_unicode_ci;

CREATE USER 'arinfotek_app'@'localhost'
IDENTIFIED BY 'replace_with_a_strong_password';

GRANT SELECT, INSERT, UPDATE, DELETE
ON arinfotek_db.*
TO 'arinfotek_app'@'localhost';

FLUSH PRIVILEGES;
```

Use a unique strong password and put the same value in `.env`.

Create a sample students table:

```sql
USE arinfotek_db;

CREATE TABLE students (
    student_id BIGINT UNSIGNED AUTO_INCREMENT PRIMARY KEY,
    full_name VARCHAR(120) NOT NULL,
    email VARCHAR(160) NOT NULL UNIQUE,
    phone VARCHAR(20),
    created_at TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP
      ON UPDATE CURRENT_TIMESTAMP
);
```

Insert sample records:

```sql
INSERT INTO students (full_name, email, phone)
VALUES
('Arun Kumar', 'arun@example.com', '9876543210'),
('Priya S', 'priya@example.com', '9876501234');
```

Try `SELECT`, `UPDATE` and `DELETE` in MySQL Workbench. Always use a correct `WHERE` clause for updates and deletes.

**Exercise:** Create the database, application user and students table.
