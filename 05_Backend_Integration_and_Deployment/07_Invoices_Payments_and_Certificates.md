# Chapter 7: Invoices, Payments and Certificates

## 7.1 Invoice list
Display invoice number, issue date, due date, amount and payment status from the backend. Treat the server as the authoritative source for invoice totals and balances.

## 7.2 Payment integration
Use a recognised payment provider's official checkout flow and backend integration. The Android app should request a payment session or order from the backend, launch the provider's approved checkout UI, then ask the backend for the final status.

Never mark an invoice as paid based only on a success screen or client callback. The backend must verify the provider's signed webhook or server-to-server payment verification response.

## 7.3 Idempotency
Use a backend-supported idempotency key for payment creation and other operations where duplicate submissions would cause harm. Do not invent your own payment verification logic in the app.

## 7.4 Certificates
The app can request a certificate list or a secure download link from the backend. Check the authenticated user's access before showing or downloading a certificate. Use a system document viewer or safe file handling.

## Practical task
Build invoice and certificate list screens. For payment, implement a sandbox/test flow only after the backend and provider verification are configured.
