# 10. Connect React or Android to Express

## React fetch example

```javascript
async function loadStudents() {
  const response = await fetch("http://localhost:5000/api/students");

  if (!response.ok) {
    throw new Error(`Request failed: ${response.status}`);
  }

  const result = await response.json();
  return result.data;
}
```

For browser-based React, configure Express CORS to allow the correct frontend origin. Use HTTPS in production.

## Android Emulator
When the API runs on the Windows host, Android Emulator reaches it through:

```text
http://10.0.2.2:5000/api/students
```

Inside the emulator, `localhost` points to the emulator itself, not Windows.

For a physical phone, use the computer's LAN IP address. Both devices must be able to reach each other. Allow the API port only on a trusted private network during development.

Use Retrofit/OkHttp from Android. Keep the API base URL in build configuration. Never put MySQL credentials or a database connection string in Android.

Android may block cleartext HTTP depending on target SDK and network security settings. Use HTTPS in production. If HTTP is temporarily enabled for local testing, scope it to debug builds and remove it from release builds.

**Exercise:** Fetch the student list from a React page or Android screen and show loading, content and error states.
