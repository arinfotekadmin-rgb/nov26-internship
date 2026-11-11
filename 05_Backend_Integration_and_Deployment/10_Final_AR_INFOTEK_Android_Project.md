# Chapter 10: Final AR INFOTEK Android Application

## Project objective
Build a student-facing Android app that communicates with the AR INFOTEK Node.js/Express backend and PostgreSQL database through documented REST APIs.

## Required modules
1. Login and logout
2. Student profile
3. Course catalogue and course details
4. Student dashboard
5. Attendance history
6. Internship progress
7. Invoice list and payment status
8. Certificate list

## Suggested screen flow

```text
Splash / Session Check
          |
          v
       Login
          |
          v
      Dashboard
       /  |  \
      /   |   \
 Profile Courses Attendance
          |
      Internship
          |
       Invoices
          |
     Certificates
```

## Technical requirements
- Kotlin and Jetpack Compose
- ViewModel and StateFlow
- Repository pattern
- Retrofit and OkHttp
- JSON serialization
- Secure session handling
- Room for suitable offline cache
- DataStore for non-sensitive preferences
- WorkManager for deferrable background refresh
- Unit and UI tests
- HTTPS production API

## Development milestones
1. Confirm and test backend API contracts.
2. Create app navigation and design system.
3. Implement authentication.
4. Implement profile and course catalogue.
5. Implement attendance and internship progress.
6. Implement invoice and certificate views.
7. Add error handling and tests.
8. Perform security and release checks.
9. Generate a signed AAB and prepare store listing assets.

## Final submission
- Android Studio project in Git.
- README with setup and build steps.
- API contract document.
- Screenshots or a short demonstration video.
- Unit and UI test results.
- Release checklist.
- List of known limitations.

## Evaluation rubric

| Area | Marks |
|---|---:|
| Architecture and Kotlin quality | 10 |
| UI and navigation | 10 |
| Authentication and session handling | 15 |
| API integration | 20 |
| Attendance and internship modules | 15 |
| Invoice, payment status and certificates | 10 |
| Error handling and testing | 10 |
| Security and release preparation | 10 |
| **Total** | **100** |

## Final review questions
1. Why must the app communicate with PostgreSQL through the backend?
2. What prevents one student from reading another student's profile?
3. Why is a payment callback from the app insufficient to confirm payment?
4. How should the app behave when the API is unavailable?
5. Which data should be cached locally and which data must remain authoritative on the server?
