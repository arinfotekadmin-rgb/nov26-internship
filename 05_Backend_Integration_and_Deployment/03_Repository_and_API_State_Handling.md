# Chapter 3: Repository and API State Handling

## 3.1 Keep networking out of composables
The composable renders state. The ViewModel coordinates screen actions. The repository obtains data from the API and, where appropriate, local storage.

## 3.2 Repository example

```kotlin
class CourseRepositoryImpl(
    private val api: CourseApi
) : CourseRepository {

    override suspend fun getCourses(): Result<List<Course>> {
        return try {
            val courses = api.getCourses().map { dto ->
                Course(
                    id = dto.id,
                    title = dto.title
                )
            }
            Result.success(courses)
        } catch (error: IOException) {
            Result.failure(error)
        } catch (error: HttpException) {
            Result.failure(error)
        }
    }
}
```

Ensure the domain model matches your actual project. Handle serialization and unexpected exceptions at a suitable boundary.

## 3.3 UI state
Represent loading, content, empty and error states explicitly. Provide a Retry action for recoverable errors.

## 3.4 HTTP status codes
Common responses:
- `200`: request succeeded.
- `201`: resource created.
- `204`: succeeded with no response body.
- `400`: invalid request.
- `401`: missing or invalid authentication.
- `403`: authenticated but not permitted.
- `404`: resource not found.
- `409`: conflict.
- `422`: validation failure, if used by your API.
- `429`: rate limit.
- `500`: server error.

Use the backend's documented error schema. Do not assume every API uses the same JSON structure.

## Practical task
Disconnect the network, return a 401 response and return a 500 response. Verify that the screen displays an appropriate message for each case.
