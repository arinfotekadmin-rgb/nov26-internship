# 5. Resources, Themes and Configuration

### Resource folders
- `values/strings.xml`: user-facing text.
- `values/`: colours, themes and dimensions.
- `drawable/`: images and vector drawables.
- `mipmap/`: launcher icons.

Keep user-facing text in string resources where practical. This helps maintenance and translation.

```xml
<resources>
    <string name="app_name">AR INFOTEK Learning</string>
    <string name="home_title">Learn. Build. Grow.</string>
</resources>
```

### AR INFOTEK brand references
- Primary blue: `#1E5AA8`
- Accent orange: `#FF891C`
- Dark background: `#0B1324`

Check text contrast and readability on small screens. Do not stretch the company logo.

### App configuration
- `applicationId`: unique installed app identifier.
- `versionCode`: integer identifying a release.
- `versionName`: human-readable release version.
- `minSdk`: oldest Android API level supported.
- `targetSdk`: Android API level the app is designed and tested against.

Choose SDK values based on your supported devices and current Play policy requirements.
