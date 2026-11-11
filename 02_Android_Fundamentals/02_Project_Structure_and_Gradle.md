# 2. Project Structure and Gradle

### Important files
- `settings.gradle.kts`: project modules and repositories.
- Root `build.gradle.kts`: project-level plugin configuration.
- `app/build.gradle.kts`: app configuration, SDK settings and dependencies.
- `gradle/libs.versions.toml`: optional dependency version catalog.
- `gradle.properties`: Gradle properties.
- Gradle Wrapper scripts: run the project's configured Gradle version.

Gradle resolves dependencies, compiles Kotlin and resources, runs tests and packages the app. The Android Gradle Plugin adds Android-specific build tasks.

### Commands (Windows PowerShell)
```powershell
.\gradlew.bat tasks
.\gradlew.bat assembleDebug
.\gradlew.bat test
```

### Practical task
Find and explain `namespace`, `applicationId`, `minSdk` and `targetSdk`. Sync Gradle, build a debug APK and locate it under the app module's build outputs.

### Common issues
- Gradle sync failure: check internet, proxy and dependency versions.
- Missing SDK: install the required platform using SDK Manager.
- JDK mismatch: use the Gradle JDK recommended by Android Studio.
- Dependency conflict: inspect the error and select compatible versions.

Do not copy old Gradle or Kotlin versions from an outdated tutorial. Use the versions supported by your installed Android Studio template.
