# Global Astronomy & Astrophysics Challenge (GAAC) 2026

An integrated web platform and examination portal for the Global Astronomy & Astrophysics Challenge (GAAC) 2026. The system supports team registration, ambassador tracking, real-time proctored online examinations, automated scoring pipelines, and verifiable digital certificates.

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Firebase](https://img.shields.io/badge/Backend-Firebase-FFCA28?logo=firebase&logoColor=black)](https://firebase.google.com/)
[![Hosting](https://img.shields.io/badge/Hosting-Vercel%20%2F%20Firebase-black)](https://vercel.com)

---

## System Overview

The platform is structured into four primary modules:

1. **Public Portal & Registration**: Event syllabus, tournament timeline, partner recognition, awards structure, and team registration (1 to 3 members per team).
2. **Ambassador & Referral System**: Referral code generation, registration attribution, leaderboard tracking, and ambassador dashboard.
3. **Proctored Examination Engine**: Secure test interface supporting full-screen enforcement, multi-angle camera/screen verification, MediaPipe-based face monitoring, violation event logging, and anti-tamper safeguards.
4. **Administration & Analytics**: Real-time candidate monitoring, question bank seeding, automated score aggregation, violation review, and automated certificate generation with QR code verification.

---

## Architecture & Tech Stack

- **Frontend**: Vanilla JavaScript (ES modules), HTML5, CSS3.
- **Backend Services**: Firebase (Firestore, Firebase Authentication, Cloud Functions, Cloud Storage).
- **Computer Vision / Proctoring**: MediaPipe Face Detection with heuristic skin-tone/brightness fallback.
- **Deployment**: Vercel (primary production frontend) and Firebase Hosting (backend rules and edge assets).
- **Certificate Verification**: Dynamic canvas rendering with embedded QR code verification endpoints.

---

## Project Structure

```
GAAC/
├── *.html                      # Application entry points and portals
├── css/                        # Responsive stylesheets and design systems
├── js/                         # Frontend application logic, security, and proctoring
├── data/                       # Official tournament rankings and static datasets
├── docs/                       # Comprehensive platform architecture and system overview
├── scripts/                    # Automation scripts and integrations
├── images/                     # Partner branding, assets, and tournament visuals
├── pdf/                        # Competition structure, syllabus, and papers
├── functions/                  # Cloud Functions for scoring, resets, and exports
├── firestore.rules             # Granular database security rules
└── README.md
```

---

## Security Model

Database access is governed by strict Firestore security rules:
- **Team Isolation**: Authenticated members can only read and write data associated with their specific team ID.
- **Examination Integrity**: Answer keys and scoring scripts are restricted to admin privileges and backend Cloud Functions. Question text is delivered without client-exposed answer keys.
- **Proctoring Telemetry**: Violation snapshots and event counts are securely piped to Cloud Storage and Firestore audit logs.

---

## Local Development

1. Clone the repository:
   ```bash
   git clone https://github.com/Adel-333/GAAC.git
   cd GAAC
   ```

2. Serve the static frontend using any local HTTP server:
   ```bash
   npx live-server
   # or
   python -m http.server 8000
   ```

3. Open `http://localhost:8000` in your browser.

---

## License

This project is licensed under the MIT License.
