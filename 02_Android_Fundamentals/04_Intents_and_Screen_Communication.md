# 4. Intents and Screen Communication

An Intent is a message requesting an action from an Android component. It can start an Activity, open a website or share text.

### Explicit Intent
```kotlin
val intent = Intent(this, CourseActivity::class.java)
intent.putExtra("course_id", 101)
startActivity(intent)
```

Read the value in the destination Activity:
```kotlin
val courseId = intent.getIntExtra("course_id", -1)
```

### Implicit Intent
```kotlin
val intent = Intent(
    Intent.ACTION_VIEW,
    Uri.parse("https://arinfotek.co.in")
)
startActivity(intent)
```

Share text:
```kotlin
val shareIntent = Intent(Intent.ACTION_SEND).apply {
    type = "text/plain"
    putExtra(Intent.EXTRA_TEXT, "Explore AR INFOTEK training programmes.")
}
startActivity(Intent.createChooser(shareIntent, "Share using"))
```

### Practical task
Create a second Activity named `CourseActivity`. Pass a sample course ID to it. Add a button that opens the AR INFOTEK website.

**Compose note:** Use Navigation Compose for in-app navigation in a modern single-Activity Compose app. Intents remain useful for external apps and system actions.
