# 13. ViewModel, UI State and Repository

### Responsibilities
- **Composable:** renders UI and forwards user events.
- **ViewModel:** holds screen-level state and coordinates UI actions.
- **Repository:** provides data from local or remote sources.
- **Data source:** performs API or database operations.

### UI state model
```kotlin
data class CoursesUiState(
    val isLoading: Boolean = false,
    val courses: List<Course> = emptyList(),
    val errorMessage: String? = null
)
```

The screen should render loading, success, empty and error states.

### Data flow
```text
User action
   ↓
Composable
   ↓ event
ViewModel
   ↓
Repository
   ↓
API / Room
   ↓
ViewModel state
   ↓
Composable renders state
```

Use lifecycle-aware state collection such as `collectAsStateWithLifecycle`, with the required lifecycle Compose dependency.

### Exercise
Move course loading logic from a composable into a ViewModel and repository. Start with a fake repository, then replace it with a real data source.
