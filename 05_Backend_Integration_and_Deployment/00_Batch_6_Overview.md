# Batch 6: Backend Integration and Deployment

**Duration:** 2 weeks  
**Prerequisites:** Batch 5, Kotlin, Compose, ViewModel, coroutines and REST API fundamentals.

## Learning outcomes
You will learn to:
- Connect the Android app to a Node.js/Express REST API.
- Exchange JSON using HTTP.
- Implement login and session handling safely.
- Display backend data through repositories and ViewModels.
- Handle validation, HTTP errors and expired sessions.
- Submit attendance, profile and course actions to the backend.
- Integrate invoice and payment status safely.
- Test API integration and prepare a release build.

## Target architecture

```text
Jetpack Compose UI
       |
       v
ViewModel + UI State
       |
       v
Repository
   |          |
   v          v
Room       Retrofit/OkHttp
              |
              | HTTPS + JSON
              v
       Node.js + Express API
              |
              v
          PostgreSQL
```

## Suggested two-week plan

| Day | Work |
|---|---|
| 1 | API contract and environment setup |
| 2 | Retrofit, DTOs and API client |
| 3 | Repository and course catalogue |
| 4 | Login and session handling |
| 5 | Student profile and dashboard |
| 6 | Attendance API integration |
| 7 | Internship progress and course actions |
| 8 | Invoice and payment status |
| 9 | Error handling, testing and security review |
| 10 | Release build and deployment checklist |

## Important security rule
The mobile application is an untrusted client. Validate identity, permissions, ownership, fees and all business rules on the Express backend. Never trust values supplied by the Android app simply because the UI displayed them.
