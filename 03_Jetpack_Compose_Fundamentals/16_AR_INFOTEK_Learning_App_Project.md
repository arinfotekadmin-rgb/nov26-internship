# 16. Project: AR INFOTEK Learning App

## Objective
Create an Android app that introduces AR INFOTEK training programmes and lets prospective learners browse courses and submit an enquiry.

### Brand references
- Organisation: AR INFOTEK
- Website: https://arinfotek.co.in
- Primary blue: `#1E5AA8`
- Accent orange: `#FF891C`
- Dark background: `#0B1324`

## Screens

### Home
- Logo and app name.
- Short introduction.
- Featured courses.
- Actions for Courses, Register and Contact.

### Course catalogue
- Course title, category, duration and delivery mode.
- Search and category filter.

### Course details
- Description and learning outcomes.
- Tools and technologies.
- Duration and intended audience.
- Enquiry action.

### Registration / enquiry
- Full name, email, mobile number, course and message.
- Field validation and submission feedback.

### Contact
Use official contact details only after verifying the current information on the company website.

## Suggested package structure
```text
com.arinfotek.learning/
  data/
    model/
    repository/
    remote/
  ui/
    components/
    navigation/
    screens/
      home/
      courses/
      details/
      register/
      contact/
    theme/
  viewmodel/
```

## Development milestones
1. Create project and theme.
2. Build static screens with sample data.
3. Add reusable course cards and lists.
4. Add navigation.
5. Add form state and validation.
6. Add ViewModels and repository.
7. Connect to a staging API.
8. Add tests and handle network failures.
9. Test multiple screen sizes.
10. Prepare a release build after security and privacy review.

## Backend integration
Coordinate with the AR INFOTEK Node.js/Express backend team. Agree on HTTPS base URL, endpoints, JSON formats, authentication, validation and error responses.

The Android app calls the backend API. The backend accesses PostgreSQL. Never embed PostgreSQL credentials in the Android app.

CORS is a browser security mechanism. Native Android HTTP clients do not use browser CORS enforcement, but server authentication and access controls still apply.

## Non-functional requirements
- Usable on common Android phone sizes.
- Clear loading, empty and error states.
- Client-side and server-side validation.
- HTTPS in staging and production.
- No secrets or personal data in logs.
- Request only necessary permissions.
- Provide a privacy notice before collecting personal data.

## Deliverables
- Android Studio project and README.
- Screen flow diagram.
- API contract document.
- Test checklist and results.
- Debug APK for internal testing.
- Release AAB after production checks.

## Acceptance checklist
- [ ] App launches without crashing.
- [ ] Navigation works.
- [ ] Course search and filters work.
- [ ] Correct course details appear.
- [ ] Invalid form submissions are rejected.
- [ ] Loading and network error states appear.
- [ ] Back navigation works.
- [ ] App works on at least two screen sizes.
- [ ] No secrets are committed to Git.
- [ ] Production API uses HTTPS.
