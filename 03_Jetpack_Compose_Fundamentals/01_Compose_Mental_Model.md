# 1. Compose Mental Model and First Screen

Compose is Android's declarative UI toolkit. You write Kotlin functions that describe what should appear on screen. When observed state changes, Compose recomposes the relevant UI.

```kotlin
@Composable
fun WelcomeScreen() {
    Text(text = "Welcome to AR INFOTEK")
}
```

A composable:
- Uses `@Composable`.
- Can call other composables.
- Describes UI.
- Accepts parameters to make it reusable.

### Host Compose in MainActivity
```kotlin
class MainActivity : ComponentActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContent {
            MaterialTheme {
                WelcomeScreen()
            }
        }
    }
}
```

Use Android Studio's Compose project template to configure compatible dependencies and plugins.

### Exercise
Create a screen with AR INFOTEK, the text “Industry-oriented IT training” and an “Explore Courses” button.
