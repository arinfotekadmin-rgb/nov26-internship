# 6. Runtime Permissions

Sensitive permissions such as camera and location require a runtime request on supported Android versions. Declare only permissions your feature needs.

### Good permission flow
1. Explain why the feature needs access.
2. Request permission when the user starts that feature.
3. Handle approval and denial.
4. Offer an alternative where possible.

### Activity Result API example
```kotlin
private val requestCameraPermission =
    registerForActivityResult(
        ActivityResultContracts.RequestPermission()
    ) { granted ->
        if (granted) {
            // Continue to camera feature.
        } else {
            // Explain that camera upload is unavailable.
        }
    }

// Call after a user action:
requestCameraPermission.launch(Manifest.permission.CAMERA)
```

Place the launcher in an Activity or suitable lifecycle-aware owner. Add the camera permission to the manifest and required imports.

### Practical task
Design a document upload screen. Request camera permission only when the user taps “Take photo”. Also provide a file picker option.

Do not request continuous location for a course catalogue. Do not collect biometric data without a clear approved requirement and suitable safeguards.
