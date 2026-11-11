# 3. Layouts: Column, Row and Box

### Column
Arranges children vertically.
```kotlin
Column(
    verticalArrangement = Arrangement.spacedBy(12.dp)
) {
    Text("AR INFOTEK")
    Text("Learn practical technology skills")
}
```

### Row
Arranges children horizontally.
```kotlin
Row(
    horizontalArrangement = Arrangement.SpaceBetween,
    verticalAlignment = Alignment.CenterVertically
) {
    Text("Popular Courses")
    Text("View all")
}
```

### Box
Places children in the same container and supports alignment and layering.
```kotlin
Box(
    modifier = Modifier.fillMaxWidth(),
    contentAlignment = Alignment.Center
) {
    Text("Learning starts here")
}
```

Use `dp` for layout dimensions and `sp` for text. Prefer flexible sizing over fixed screen dimensions.

### Exercise
Build a home screen with a header, welcome section, two course cards and a bottom action. Test a narrow phone and a larger device.
