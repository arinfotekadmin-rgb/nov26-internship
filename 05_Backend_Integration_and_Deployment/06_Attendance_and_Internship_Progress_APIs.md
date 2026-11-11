# Chapter 6: Attendance and Internship Progress APIs

## 6.1 Attendance history
A history endpoint may return:
- Attendance record ID
- Date and time
- Session or batch
- Status
- Optional reason or note

Use server timestamps and the backend's attendance status definitions.

## 6.2 Mark attendance
A suggested request may contain a session identifier and location data if the attendance policy requires it. The backend must verify:
- The authenticated student is enrolled in the session.
- The session is open for attendance.
- The timestamp is valid.
- Location and geofence rules are satisfied.
- A duplicate attendance record does not already exist.

Do not allow the Android app to decide that attendance is valid by itself.

## 6.3 Location handling
Ask for location permission only when the student starts attendance. Explain the purpose. Handle denied permission, unavailable GPS and low accuracy. Send only the location information required by the policy.

## 6.4 Internship progress
Display assigned tasks, due dates, status, mentor feedback and completion percentage if the backend provides them. The backend must enforce who can update task status and feedback.

## Practical task
Implement attendance history and internship progress screens using test data first, then connect the actual API endpoints.
