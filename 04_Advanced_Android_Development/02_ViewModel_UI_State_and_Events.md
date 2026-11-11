# Chapter 2: ViewModel, UI State and Events

## 2.1 ViewModel
A ViewModel holds screen-related state across configuration changes such as device rotation. It should not hold Activity, View or composable references.

## 2.2 Model screen state explicitly

```kotlin
data class CoursesUiState(
    val isLoading: Boolean = false,
    val courses: List<Course> = emptyList(),
    val errorMessage: String? = null
)
```

A screen can then render loading, content, empty and error states consistently.

## 2.3 ViewModel example

```kotlin
class CoursesViewModel(
    private val repository: CourseRepository
) : ViewModel() {

    private val _uiState = MutableStateFlow(CoursesUiState())
    val uiState: StateFlow<CoursesUiState> = _uiState.asStateFlow()

    fun loadCourses() {
        viewModelScope.launch {
            _uiState.update { it.copy(isLoading = true, errorMessage = null) }

            repository.getCourses()
                .onSuccess { items ->
                    _uiState.value = CoursesUiState(courses = items)
                }
                .onFailure { error ->
                    _uiState.value = CoursesUiState(
                        errorMessage = error.message ?: "Unable to load courses"
                    )
                }
        }
    }
}
```

This example assumes `CourseRepository.getCourses()` returns `Result<List<Course>>`.

## 2.4 Collect state in Compose

```kotlin
@Composable
fun CoursesRoute(viewModel: CoursesViewModel) {
    val state by viewModel.uiState.collectAsStateWithLifecycle()

    LaunchedEffect(Unit) {
        viewModel.loadCourses()
    }

    CoursesScreen(state = state)
}
```

Use the lifecycle-aware Compose collection API and add its required lifecycle-runtime-compose dependency.

## 2.5 UI events
Examples include tapping Retry, selecting a course or submitting a form. Pass events to the ViewModel through functions. Keep navigation decisions in the UI/navigation layer unless your app architecture explicitly centralises them.

## Practical task
Create a DashboardViewModel with `isLoading`, `studentName`, `courseCount` and `errorMessage`. Build loading, success and error UI states.

## Check your understanding
1. What problem does ViewModel solve?
2. Why use StateFlow for screen state?
3. What should happen when the user taps Retry?
4. Why use `collectAsStateWithLifecycle()`?
