# Chapter 1: App Architecture and Package Structure

## 1.1 Why architecture matters
As an app grows, putting navigation, API calls, validation and UI code into one Activity or composable becomes difficult to maintain. Separate responsibilities so each part has a clear purpose.

## 1.2 Recommended layers

- **UI layer:** Compose screens, reusable components and UI state.
- **Domain layer:** Business rules and use cases. Add this when the rules become complex.
- **Data layer:** Repositories, local database, preferences and remote data sources.

A small app does not need a class for every operation. Keep the structure understandable and introduce abstractions when they solve a real problem.

## 1.3 Suggested package structure

```text
com.arinfotek.learningapp/
  core/
    common/
    designsystem/
    network/
  data/
    local/
    remote/
    repository/
  domain/
    model/
    repository/
    usecase/
  feature/
    auth/
    dashboard/
    courses/
    attendance/
    profile/
  navigation/
  MainActivity.kt
```

## 1.4 Repository responsibility
A repository provides a stable interface to the rest of the app. It decides whether data comes from a remote API, local database or cache.

```kotlin
interface CourseRepository {
    suspend fun getCourses(): Result<List<Course>>
}
```

For a larger project, define the interface in the domain layer and implement it in the data layer.

## 1.5 Dependency direction
UI code should depend on ViewModels or UI-facing state holders. ViewModels should depend on repository interfaces or concrete repositories supplied through dependency injection. Data sources should not depend on Compose screens.

## Practical task
Create `feature/courses`, `data/repository` and `domain/model` packages. Move course-related code into the appropriate locations. Confirm that the app still builds.

## Check your understanding
1. What responsibility belongs in a repository?
2. Why should a composable avoid making a network request directly?
3. When would a domain/use-case layer be useful?
4. What is the difference between a data source and a repository?
