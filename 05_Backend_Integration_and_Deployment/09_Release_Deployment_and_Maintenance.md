# Chapter 9: Release, Deployment and Maintenance

## 9.1 Backend deployment checklist
- Deploy the Express API to a production host.
- Configure production environment variables.
- Use a managed PostgreSQL database or a properly secured database server.
- Restrict database network access.
- Run database migrations.
- Configure HTTPS.
- Configure backups and test restoration.
- Set up server logs, monitoring and health checks.
- Verify authentication, authorization and rate limits.

## 9.2 Android release checklist
- Use the production HTTPS API base URL.
- Confirm no test credentials or debug endpoints remain.
- Set application ID, version code and version name.
- Configure app icon, name and privacy disclosures.
- Test on physical devices and different Android versions.
- Test slow, unstable and unavailable networks.
- Generate a signed AAB.
- Protect signing keys and back them up securely.
- Review current Google Play policy and target API requirements before submission.

## 9.3 Release build
In Android Studio, use Build > Generate Signed Bundle / APK and select Android App Bundle when preparing a Play release. Keep the signing key and passwords outside source control.

## 9.4 Monitoring and support
Track app version, non-sensitive crash diagnostics and API health. Do not collect unnecessary student information. Provide a support contact and a clear way to report problems.

## Practical task
Generate a signed test release. Install it on a physical phone and verify login, course list, profile, logout and offline behaviour.
