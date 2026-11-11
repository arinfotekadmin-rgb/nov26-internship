# 3. Activity Lifecycle

Android can pause, stop or recreate an Activity as the user moves between apps or device configuration changes.

### Main callbacks
- `onCreate()`: initial setup.
- `onStart()`: Activity becomes visible.
- `onResume()`: Activity enters the foreground.
- `onPause()`: Activity is losing foreground focus.
- `onStop()`: Activity is no longer visible.
- `onRestart()`: stopped Activity is starting again.
- `onDestroy()`: Activity is being destroyed. Do not rely on this callback to save critical data.

Typical sequence:
```text
onCreate -> onStart -> onResume
onPause -> onStop
onRestart -> onStart -> onResume
```

### Observe lifecycle events
```kotlin
class MainActivity : ComponentActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        Log.d("ARLifecycle", "onCreate")
        setContent { Text("AR INFOTEK") }
    }

    override fun onStart() {
        super.onStart()
        Log.d("ARLifecycle", "onStart")
    }

    override fun onResume() {
        super.onResume()
        Log.d("ARLifecycle", "onResume")
    }
}
```
Add the required imports, including `android.util.Log`.

### Practical task
Observe Logcat while opening another app, returning to your app and rotating the emulator. Record the callback sequence.

Do not perform long-running work directly in lifecycle callbacks. Use lifecycle-aware APIs and suitable background work tools.
