# 10. Debugging, Testing and Build Variants

### Android Studio tools
- Logcat: inspect logs and crashes.
- Breakpoints: pause execution.
- Debugger: inspect variables.
- Layout Inspector: inspect runtime UI.
- Profiler: investigate CPU, memory and network.
- App Inspection: inspect supported databases and background work.

Example:
```kotlin
Log.d("CourseScreen", "Loaded ${courses.size} courses")
```

Never log passwords, tokens, personal records or payment information.

### Testing levels
- Unit test: tests a function or class.
- UI test: checks user interaction and visible behaviour.
- Integration test: checks multiple components together.

### Build variants
- `debug`: development build with debugging support.
- `release`: production-oriented build, optimized as configured.

Use separate development and production API base URLs. Do not ship test credentials in a release build.

### Practical task
Introduce a validation bug, reproduce it, inspect it with the debugger and fix it. Run unit tests and create a debug APK.
