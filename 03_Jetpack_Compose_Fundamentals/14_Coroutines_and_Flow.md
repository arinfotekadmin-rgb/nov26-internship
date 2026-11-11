# 14. Coroutines and Flow

Kotlin coroutines support asynchronous work without blocking the main thread.

Key concepts:
- `suspend`: function can suspend without blocking a thread.
- `CoroutineScope`: defines coroutine lifetime.
- `viewModelScope`: scope tied to a ViewModel.
- `Dispatchers.IO`: commonly used for blocking I/O operations.
- `Flow`: asynchronous stream of values.

Simplified example:
```kotlin
class CoursesViewModel(
    private val repository: CourseRepository
) : ViewModel() {

    private val _uiState = MutableStateFlow(CoursesUiState())
    val uiState: StateFlow<CoursesUiState> = _uiState

    fun loadCourses() {
        viewModelScope.launch {
            _uiState.value = CoursesUiState(isLoading = true)
            try {
                val result = repository.getCourses()
                _uiState.value = CoursesUiState(courses = result)
            } catch (exception: Exception) {
                _uiState.value = CoursesUiState(
                    errorMessage = "Unable to load courses"
                )
            }
        }
    }
}
```

Add imports, dependencies and a ViewModel factory or dependency injection setup as appropriate. Avoid displaying raw exception details to users.

### Exercise
Simulate a slow course request. Show a loading indicator, then data. Simulate failure and add retry.
