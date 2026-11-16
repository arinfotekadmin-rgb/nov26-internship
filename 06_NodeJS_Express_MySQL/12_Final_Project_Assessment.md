# 12. Final Project: AR INFOTEK Student Management API

Build an Express backend connected to MySQL.

## Required modules
1. Student CRUD.
2. Course CRUD.
3. Student-course enrolment.
4. Login with password hash verification.
5. Authenticated student profile.
6. Central error handling.
7. Environment configuration.
8. Postman API tests.

## Suggested course table

```sql
CREATE TABLE courses (
    course_id BIGINT UNSIGNED AUTO_INCREMENT PRIMARY KEY,
    course_name VARCHAR(150) NOT NULL,
    description TEXT,
    duration_hours INT UNSIGNED,
    fee DECIMAL(10,2) NOT NULL DEFAULT 0,
    created_at TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP
);
```

## Suggested enrolment table

```sql
CREATE TABLE student_courses (
    enrolment_id BIGINT UNSIGNED AUTO_INCREMENT PRIMARY KEY,
    student_id BIGINT UNSIGNED NOT NULL,
    course_id BIGINT UNSIGNED NOT NULL,
    enrolled_at TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP,
    UNIQUE KEY uq_student_course (student_id, course_id),
    CONSTRAINT fk_sc_student
      FOREIGN KEY (student_id) REFERENCES students(student_id),
    CONSTRAINT fk_sc_course
      FOREIGN KEY (course_id) REFERENCES courses(course_id)
);
```

Create a separate `users` table for login credentials. Do not store passwords in the student profile table.

## Submission checklist
- Git repository with `.env` excluded.
- `.env.example`.
- SQL script for database and tables.
- API endpoint documentation.
- Postman collection or test evidence.
- README with installation and startup steps.

## Assessment rubric

| Area | Marks |
|---|---:|
| Node.js and Express setup | 10 |
| Project structure and dotenv | 10 |
| MySQL schema and relationships | 15 |
| mysql2 connection pool | 15 |
| CRUD REST APIs | 20 |
| Validation and error handling | 10 |
| Authentication and security | 10 |
| Testing and documentation | 10 |
| **Total** | **100** |

## Viva questions
1. What is Node.js?
2. What does Express do?
3. What does dotenv do?
4. Why use mysql2/promise?
5. What is a connection pool?
6. Explain GET, POST, PUT and DELETE.
7. What is a parameterised query?
8. Differentiate authentication and authorization.
9. Why should `.env` not be committed?
10. Why should Android call the API instead of connecting directly to MySQL?
