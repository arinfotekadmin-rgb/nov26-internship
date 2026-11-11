# Chapter 9: Release Preparation and Batch 5 Project

## 9.1 Release checklist
- Set application ID and version.
- Set app name, icon and launch theme.
- Remove test credentials and debug endpoints.
- Check permissions and privacy disclosures.
- Confirm HTTPS API endpoints.
- Test on at least one physical device.
- Test small and large screen sizes.
- Check accessibility labels and text scaling.
- Run unit and UI tests.
- Generate a signed Android App Bundle (AAB) for Play distribution.

## 9.2 Build variants
Use separate development and production configurations. Keep API base URLs in build configuration or an appropriate configuration layer. Never embed private backend secrets in the APK or AAB.

## 9.3 Batch 5 project: Student Dashboard
Build:
- Dashboard screen with student summary.
- Saved courses backed by Room.
- Settings backed by DataStore.
- Refresh status updated through WorkManager.
- Loading, empty and error states.
- Unit and UI tests.

## Submission
Submit:
1. Git repository.
2. Screenshots of the dashboard, saved courses and settings.
3. Test results.
4. A short README with build instructions.
5. A list of permissions and the reason for each.

## Assessment rubric

| Area | Marks |
|---|---:|
| Architecture and code organisation | 15 |
| ViewModel and UI state | 15 |
| Room and DataStore | 20 |
| WorkManager and permissions | 15 |
| Error handling and diagnostics | 10 |
| Tests | 15 |
| Documentation and Git history | 10 |
| **Total** | **100** |
