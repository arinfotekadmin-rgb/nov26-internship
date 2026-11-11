# 9. REST API and Networking

A REST API exposes resources through HTTP endpoints.

Illustrative AR INFOTEK API:
- `GET /api/courses`: list courses.
- `GET /api/courses/101`: get one course.
- `POST /api/enquiries`: submit an enquiry.
- `POST /api/students`: register a student.

HTTP methods:
- GET retrieves data.
- POST creates or submits data.
- PUT/PATCH updates data.
- DELETE removes data.

Common status codes: 200 success, 201 created, 400 invalid request, 401 authentication required, 403 forbidden, 404 not found and 500 server error.

### Android networking rules
- Add `android.permission.INTERNET` to the manifest.
- Use a library such as Retrofit or Ktor Client.
- Run network operations away from the main thread, commonly with coroutines.
- Parse JSON into Kotlin data classes.
- Show loading, success, empty and error states.
- Use HTTPS in production.
- Never hardcode production secrets in the Android app.

Example response model:
```kotlin
data class CourseDto(
    val id: Int,
    val title: String,
    val duration: String
)
```

### Practical task
Fetch sample courses from a public test API or local mock server. Display loading, error and success states.

Before connecting the AR INFOTEK Node.js/Express and PostgreSQL backend, agree on base URLs, endpoints, JSON formats, authentication, validation and error responses. The Android app must call the backend API. Never connect directly to PostgreSQL from the mobile app.
