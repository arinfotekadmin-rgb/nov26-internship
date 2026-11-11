# 4. Modifiers and Styling

A `Modifier` changes layout, drawing, interaction or semantics.

Common modifiers:
- `fillMaxWidth()`
- `fillMaxSize()`
- `padding(16.dp)`
- `size(48.dp)`
- `background(color)`
- `border(width, color, shape)`
- `clip(shape)`
- `clickable { }`
- `weight(1f)` inside Row or Column scopes

Example:
```kotlin
Card(
    modifier = Modifier
        .fillMaxWidth()
        .padding(horizontal = 16.dp),
    shape = RoundedCornerShape(12.dp)
) {
    Column(modifier = Modifier.padding(16.dp)) {
        Text("Python Full Stack Development")
        Text("30 Hours")
    }
}
```

Modifier order matters. Padding before a background can look different from padding after a background.

### Exercise
Create a course card with rounded corners, 16 dp internal padding, title, duration and a clickable details action.
