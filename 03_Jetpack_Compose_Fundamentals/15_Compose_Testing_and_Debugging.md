# 15. Compose Testing and Debugging

Compose UI tests find elements through semantics such as text, content descriptions and test tags.

Typical test flow:
1. Launch the composable under test.
2. Find a UI element.
3. Perform an action.
4. Assert the expected state.

Example test concept:
```kotlin
composeTestRule.setContent {
    WelcomeScreen()
}

composeTestRule
    .onNodeWithText("Welcome to AR INFOTEK")
    .assertIsDisplayed()
```

Use Compose UI testing dependencies compatible with your project.

### Tools
- Preview for component checks.
- Layout Inspector for runtime UI.
- Logcat for exceptions and logs.
- Breakpoints for state and event flow.
- TalkBack for accessibility checks.

### Exercise
Write tests for the home title, course card visibility, search filtering, empty form validation and navigation to course details.
