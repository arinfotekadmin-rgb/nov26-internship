# 7. Lists and RecyclerView Concepts

A course catalogue may contain many records. A list component should create visible rows efficiently.

RecyclerView is the traditional Android Views component for efficient scrolling lists. Compose uses `LazyColumn` and `LazyRow`.

```kotlin
data class Course(
    val id: Int,
    val title: String,
    val duration: String,
    val mode: String
)
```

RecyclerView terms:
- Adapter: connects data to item views.
- ViewHolder: holds item view references.
- LayoutManager: controls list arrangement.
- DiffUtil: calculates changes between lists.

Compose equivalent:
```kotlin
LazyColumn {
    items(courses, key = { it.id }) { course ->
        Text(course.title)
    }
}
```

### Practical task
Create 10 sample AR INFOTEK courses. Display title, duration and delivery mode in a scrolling list. Use stable unique IDs as keys.
