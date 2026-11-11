# 9. LazyColumn and Course Catalogue

`LazyColumn` creates visible list items as needed. It is suitable for a course catalogue.

```kotlin
data class Course(
    val id: Int,
    val title: String,
    val duration: String,
    val category: String
)

@Composable
fun CourseList(courses: List<Course>) {
    LazyColumn(
        contentPadding = PaddingValues(16.dp),
        verticalArrangement = Arrangement.spacedBy(12.dp)
    ) {
        items(
            items = courses,
            key = { course -> course.id }
        ) { course ->
            CourseCard(
                title = course.title,
                duration = course.duration
            )
        }
    }
}
```

Use stable unique keys. Avoid list indices as keys when items may be inserted, removed or reordered.

### Exercise
Create 12 sample courses covering Python, Java, Web Development, Android, Cloud and Data Analytics. Add search and category filtering.
