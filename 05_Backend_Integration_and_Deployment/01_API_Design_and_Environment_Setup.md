# Chapter 1: API Design and Environment Setup

## 1.1 Define the API contract first
Before writing Android networking code, document each endpoint:
- HTTP method and path
- Authentication requirement
- Request JSON
- Success response JSON
- Error response JSON
- Validation rules
- Expected status codes

Example API contract:

| Operation | Method | Example path |
|---|---|---|
| Login | POST | `/api/auth/login` |
| Current student | GET | `/api/students/me` |
| Course list | GET | `/api/courses` |
| Course detail | GET | `/api/courses/{id}` |
| Attendance history | GET | `/api/attendance/me` |
| Internship progress | GET | `/api/internships/me/progress` |
| Invoice list | GET | `/api/invoices/me` |

These are suggested paths. Confirm or implement them in your actual Express backend before using them in the Android app.

## 1.2 Environment URLs
Use different base URLs for emulator, physical phone and production.

- Android Emulator to host computer: `http://10.0.2.2:PORT/`
- Physical phone: use your development computer's LAN IP and ensure both devices share the network.
- Production: use your HTTPS domain, for example `https://api.example.com/`.

Replace the example production domain with the actual API domain. Do not assume the website domain and API domain are the same.

## 1.3 Android cleartext traffic
Prefer HTTPS. Android may block cleartext HTTP depending on target SDK and network security configuration. Use HTTP only for controlled local development, never for production credentials or real student data.

## 1.4 CORS
CORS is primarily enforced by browsers. Native Android HTTP clients do not use browser CORS enforcement. Your Express API still needs proper authentication, authorization, input validation and rate limiting.

## Practical task
Write an API contract for login, course list, student profile and attendance history. Test every endpoint with a REST client before connecting Android.
