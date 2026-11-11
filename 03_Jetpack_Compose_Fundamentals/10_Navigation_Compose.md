# 10. Navigation Compose

Use Navigation Compose to move between destinations in a single-Activity Compose app.

Suggested destinations:
- `home`
- `courses`
- `course/{courseId}`
- `register`
- `contact`

Conceptual example:
```kotlin
NavHost(
    navController = navController,
    startDestination = "home"
) {
    composable("home") {
        HomeScreen(
            onCoursesClick = {
                navController.navigate("courses")
            }
        )
    }

    composable("courses") {
        CourseListScreen(
            onCourseClick = { id ->
                navController.navigate("course/$id")
            }
        )
    }
}
```

Add the Navigation Compose dependency using current official Android documentation. Complete the route definitions, imports and screen parameters in your project.

### Navigation rules
- Pass identifiers rather than large data objects where practical.
- Validate route arguments.
- Handle back navigation.
- Avoid a separate Activity for every Compose screen.
- Keep navigation decisions outside low-level reusable UI components.

### Exercise
Connect Home, Courses, Course Details, Register and Contact. Test system back behaviour.
