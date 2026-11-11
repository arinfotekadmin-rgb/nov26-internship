# Chapter 8: Unit, UI and Integration Testing

## 8.1 Test levels
- **Unit tests:** Test individual functions, ViewModels and business rules.
- **UI tests:** Check visible behaviour and user interactions.
- **Integration tests:** Check whether multiple components work together, such as repository plus database.

## 8.2 Example unit test
A ViewModel test should use a fake repository so it does not depend on a live server.

```kotlin
class FakeCourseRepository : CourseRepository {
    override suspend fun getCourses(): Result<List<Course>> =
        Result.success(
            listOf(Course(id = 1, title = "Kotlin Basics"))
        )
}
```

The exact test setup depends on the ViewModel constructor and coroutine test dependencies.

## 8.3 Compose UI tests
Use semantics to locate controls and verify user-visible results.

```kotlin
composeTestRule.setContent {
    Text("AR INFOTEK Learning")
}

composeTestRule
    .onNodeWithText("AR INFOTEK Learning")
    .assertIsDisplayed()
```

## 8.4 Test cases for the learning app
1. Login form rejects blank input.
2. Course screen shows a loading indicator while loading.
3. Course screen shows an empty state when there are no courses.
4. Retry calls the repository again.
5. Saved course remains after app restart.
6. Logout clears the active session.
7. Payment status screen does not allow a user to modify payment status locally.

## Practical task
Write at least five unit or UI tests. Include one failure-state test and one persistence test.

## Check your understanding
1. What should a unit test isolate?
2. What does a fake repository provide?
3. Why test error states?
