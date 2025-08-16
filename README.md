# Digiverifier – Full Stack (Backend + Frontend)

Generated: 2025-08-16

## Quick Start (Local)

### Backend
```bash
cd backend
cp .env.example .env
# Edit .env (SMTP, JWT, etc.)
npm install
npm start
```

### Frontend
```bash
cd frontend
npm install
npm run dev
# open http://localhost:5173
```

## Core Endpoints
- POST `/api/v1/candidates/upload` – CSV/XLSX upload (columns: Name, Mobile Number, Email Id, Applicant Id, DV - Id, CC)
- POST `/api/v1/invitations` – send invite email with link from noreply
- POST `/api/v1/verifications/start` – start by token
- POST `/api/v1/verifications/:id/loa/upload` – upload LOA (PDF)
- POST `/api/v1/verifications/:id/digilocker` – Aadhaar + PIN
- POST `/api/v1/verifications/:id/itr` – PAN + password
- POST `/api/v1/verifications/:id/uan-choice` – Yes/No
- POST `/api/v1/verifications/:id/epfo` – UAN + password + captcha (OTP sent)
- POST `/api/v1/verifications/:id/epfo/otp` – OTP submission
- GET  `/api/v1/verifications/:id/steps` – step status
- POST `/api/v1/verifications/:id/complete` – finalize + emails

## Notes
- This code simulates external portal integrations (Digilocker/ITR/EPFO). Replace with official adapters when available.
- File uploads saved to `uploads/`. Change via `FILE_UPLOAD_DIR`.
- Use reverse proxy + HTTPS in production.