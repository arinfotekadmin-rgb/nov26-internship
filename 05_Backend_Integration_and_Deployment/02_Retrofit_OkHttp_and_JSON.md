# Chapter 2: Retrofit, OkHttp and JSON

## 2.1 Responsibilities
- Retrofit maps API interfaces to HTTP requests.
- OkHttp performs HTTP communication and supports interceptors and timeouts.
- Kotlin serialization or Moshi converts JSON into Kotlin data classes.

Choose one JSON converter and use it consistently.

## 2.2 DTO example
A DTO represents the API response shape. Keep it separate from UI models when API and UI requirements differ.

```kotlin
@Serializable
data class CourseDto(
    val id: Long,
    val title: String,
    val description: String? = null
)
```

## 2.3 API interface example

```kotlin
interface CourseApi {
    @GET("api/courses")
    suspend fun getCourses(): List<CourseDto>

    @GET("api/courses/{id}")
    suspend fun getCourse(
        @Path("id") id: Long
    ): CourseDto
}
```

## 2.4 Retrofit client
Add compatible stable versions of Retrofit, OkHttp and the chosen JSON converter through the Gradle version catalog or module dependencies. Check current official documentation for versions.

```kotlin
val retrofit = Retrofit.Builder()
    .baseUrl(BuildConfig.API_BASE_URL)
    .addConverterFactory(
        Json.asConverterFactory("application/json".toMediaType())
    )
    .build()

val courseApi = retrofit.create(CourseApi::class.java)
```

This snippet assumes Kotlin serialization and the relevant imports and dependencies are configured. The base URL must end with `/`.

## 2.5 Timeouts
Configure connection, read and write timeouts using OkHttp. Do not retry non-idempotent requests blindly. A payment or attendance submission may create duplicate records if retried without backend idempotency support.

## Practical task
Connect the course list endpoint. Convert DTOs into app models and display them using LazyColumn.
