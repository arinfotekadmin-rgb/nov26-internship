# 5. Material 3 Components and Themes

Material 3 provides standard components with consistent behaviour and accessibility semantics.

Useful components:
- `Scaffold`
- `TopAppBar`
- `NavigationBar`
- `Button` and `OutlinedButton`
- `Card`
- `TextField` and `OutlinedTextField`
- `AlertDialog`
- `CircularProgressIndicator`
- `SnackbarHost`

### AR INFOTEK palette
```kotlin
val ARBlue = Color(0xFF1E5AA8)
val AROrange = Color(0xFFFF891C)
val ARDark = Color(0xFF0B1324)
```

Define colours centrally in your app theme instead of repeating values on every screen. Check contrast for text, buttons and disabled states. Consider light and dark themes if required.

### Exercise
Build a branded `Scaffold` with a top app bar, screen content and bottom navigation placeholder.
