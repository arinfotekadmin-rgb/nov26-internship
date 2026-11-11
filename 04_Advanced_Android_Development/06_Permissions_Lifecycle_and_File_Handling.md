# Chapter 6: Permissions, Lifecycle and File Handling

## 6.1 Request permissions only when needed
Explain the feature before requesting access. Ask for the minimum permission required. Handle denial and permanent denial gracefully.

Examples:
- Camera permission for capturing a profile image.
- Location permission for a location-based attendance feature.
- Notification permission where required by the Android version and app behaviour.

## 6.2 Location attendance
For attendance, request location only when the student starts the attendance action. Validate the submitted coordinates and attendance rules on the backend. A mobile device's GPS result alone cannot prove that a student is physically present.

Consider accuracy, stale locations, mock-location signals, server-side geofencing and audit records. Explain location use clearly in the app.

## 6.3 Activity lifecycle
Understand `onCreate`, `onStart`, `onResume`, `onPause`, `onStop` and `onDestroy`. Do not assume an Activity remains alive in the background. Save important UI state in a ViewModel and persistent data in a suitable store.

## 6.4 File selection
Use Android's Storage Access Framework or Photo Picker where suitable. Avoid broad storage permissions when a system picker can provide access to a selected file.

## Practical task
Create a profile image selection flow using the system Photo Picker. Add permission denial handling to a sample location feature.

## Check your understanding
1. Why should permissions be requested in context?
2. What happens when Android stops an Activity?
3. Why should attendance validation happen on the backend?
4. What is the benefit of a system file picker?
