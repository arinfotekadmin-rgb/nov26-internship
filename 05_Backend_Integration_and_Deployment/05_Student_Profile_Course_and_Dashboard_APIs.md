# Chapter 5: Student Profile, Course and Dashboard APIs

## 5.1 Student profile
Display only fields returned by the authenticated profile endpoint, such as:
- Student name
- Student identifier
- Email or phone, if permitted
- Programme or department
- Enrolled course summary

The backend must determine which student record belongs to the authenticated account.

## 5.2 Course catalogue
Typical operations:
- List courses
- View course details
- View course modules
- View enrolment status

Use pagination if the course catalogue can grow. Do not download every record without a limit.

## 5.3 Dashboard aggregation
A dashboard endpoint can return a summary of course count, attendance percentage and internship status. Alternatively, the Android app can call multiple endpoints. Choose based on API design, performance and caching requirements.

## 5.4 Refresh
Use pull-to-refresh or a visible refresh action. Prevent repeated taps from starting duplicate requests. Keep the previous content visible when refreshing if that provides a better experience.

## Practical task
Build a dashboard that loads the authenticated student's profile and course summary. Include loading, empty and error states.
