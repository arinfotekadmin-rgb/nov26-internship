# 08. Test REST APIs with Postman

Start the backend:

```powershell
npm run dev
```

Assume the API runs at `http://localhost:5000`.

## List students
- Method: GET
- URL: `http://localhost:5000/api/students`
- Expected: 200

## Create student
- Method: POST
- URL: `http://localhost:5000/api/students`
- Header: `Content-Type: application/json`
- Body, raw JSON:

```json
{
  "full_name": "Karthik Raj",
  "email": "karthik@example.com",
  "phone": "9876543210"
}
```

Expected: 201 and a new `student_id`.

## Read one student
GET `http://localhost:5000/api/students/1`

Use the ID returned by your POST request.

## Update student
- Method: PUT
- URL: `http://localhost:5000/api/students/1`
- Body:

```json
{
  "full_name": "Karthik R",
  "email": "karthik@example.com",
  "phone": "9000000000"
}
```

Expected: 200.

## Delete student
DELETE `http://localhost:5000/api/students/1`

Expected: 200. A later GET for that ID should return 404.

## Negative tests
Try a missing name, invalid ID, duplicate email and non-existent ID. Record the HTTP status and response.
