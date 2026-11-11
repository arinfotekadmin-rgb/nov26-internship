# 1. Android Platform and App Structure

## Learning objectives
- Explain Android OS, Android SDK and Android application packages.
- Identify the main parts of an Android project.
- Understand the Android manifest and launcher Activity.

Android is an operating system based on the Linux kernel. Apps run in separate processes and application sandboxes. The Android framework provides APIs for UI, storage, notifications, sensors and device features.

### Key terms
- **Android SDK:** APIs and tools used to build Android apps.
- **APK:** installable Android application package.
- **AAB:** Android App Bundle, commonly used for Play Store distribution.
- **Manifest:** declares app components, permissions and metadata.
- **Activity:** an app component that provides an entry point for user interaction.
- **Resource:** non-code content such as strings, icons and images.

### Typical project structure
```text
app/
  src/main/
    AndroidManifest.xml
    java/com/example/arinfotek/
      MainActivity.kt
    res/
      drawable/
      mipmap/
      values/
  build.gradle.kts
build.gradle.kts
settings.gradle.kts
```

### Launcher Activity
The manifest identifies the launcher Activity using `MAIN` and `LAUNCHER` intent-filter entries. Components with intent filters must declare `android:exported` on modern Android versions.

### Practical task
1. Create a Kotlin Android project.
2. Set the app label to `AR INFOTEK Learning`.
3. Locate `AndroidManifest.xml` and `MainActivity.kt`.
4. Identify `applicationId` in the app Gradle file.
5. Run the app on an emulator.

### Review
1. What is the Android SDK?
2. What does the manifest declare?
3. What is an Activity?
4. How do APK and AAB differ?
