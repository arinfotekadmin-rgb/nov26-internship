# 2. Composable Functions and Previews

Break a screen into small reusable functions.

```kotlin
@Composable
fun CourseTitle(title: String, duration: String) {
    Column {
        Text(text = title)
        Text(text = duration)
    }
}
```

Use previews to inspect components without launching the full app.

```kotlin
@Preview(showBackground = true)
@Composable
fun CourseTitlePreview() {
    MaterialTheme {
        CourseTitle(
            title = "Full Stack Web Development",
            duration = "30 Hours"
        )
    }
}
```

### Exercise
Create reusable composables named `AppHeader`, `SectionTitle`, `CourseCard`, `PrimaryActionButton` and `AppFooter`. Add previews where practical.

Avoid placing an entire app inside one large composable.
