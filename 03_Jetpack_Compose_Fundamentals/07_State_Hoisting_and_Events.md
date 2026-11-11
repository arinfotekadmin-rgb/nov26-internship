# 7. State Hoisting and UI Events

State hoisting moves state to a common parent. The parent passes the current value and a callback to the child.

```kotlin
@Composable
fun SearchBox(
    query: String,
    onQueryChange: (String) -> Unit
) {
    OutlinedTextField(
        value = query,
        onValueChange = onQueryChange,
        label = { Text("Search courses") },
        modifier = Modifier.fillMaxWidth()
    )
}
```

Parent owns the state:
```kotlin
@Composable
fun CourseSearchScreen() {
    var query by rememberSaveable { mutableStateOf("") }

    SearchBox(
        query = query,
        onQueryChange = { query = it }
    )
}
```

State flows down; events flow up. This makes child components reusable and easier to test.

### Exercise
Build a reusable search field. The parent filters the course list as the user types.
