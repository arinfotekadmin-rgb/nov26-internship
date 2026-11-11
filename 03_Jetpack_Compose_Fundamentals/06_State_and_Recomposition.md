# 6. State and Recomposition

State is a value that can change while the app runs and affects what the user sees. Examples include a selected tab, text in a field, loading status and selected course.

```kotlin
@Composable
fun CounterExample() {
    var count by remember { mutableIntStateOf(0) }

    Column {
        Text("Count: $count")
        Button(onClick = { count++ }) {
            Text("Add")
        }
    }
}
```

Use `rememberSaveable` for simple UI state that should survive Activity recreation when supported by its saved-state mechanism. Do not use `remember` as persistent storage or as a replacement for a ViewModel.

Recomposition reruns composable functions when relevant state changes. Avoid network calls, database writes and one-time side effects directly in a composable body.

### Exercise
Create a course filter with two selectable categories. Display only courses in the selected category.
