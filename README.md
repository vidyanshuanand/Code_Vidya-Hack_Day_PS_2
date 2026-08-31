# CertiFlow AI
### Dynamic Certificate Generation & Verification Portal — Code Vidya Hack Solo PS 2

CertiFlow AI is an end-to-end prototype for managing event certificates at scale. It combines structured validation rules with an AI-ready validation layer, human review, bulk certificate generation, unique certificate IDs, and QR-based public verification.

## Problem Statement
College events may involve hundreds or thousands of participants. Manual certificate workflows create incorrect names, duplicate records, missing information, formatting problems, and difficulty verifying authenticity.

## Proposed Solution
A centralized workflow:
**Event → CSV Upload → AI-assisted Cleaning/Validation → Human Review → Bulk Generation → Unique ID + QR → Public Verification**

## Key Features
- Event and certificate template management
- Bulk CSV participant upload
- AI-assisted data cleaning and validation workflow
- Duplicate, missing-field and invalid-email detection
- Human review and correction queue
- Bulk certificate generation
- Unique certificate IDs
- QR-based verification
- Public verification UI
- Responsive dashboard

## Technology / Tech Stack
- Frontend: HTML5, CSS3, Vanilla JavaScript
- UI: Custom responsive dashboard, CSS gradients and components
- Data: In-browser JavaScript state for the prototype
- CSV: FileReader + client-side CSV parsing
- QR: QRCode.js
- Certificate: Print-to-PDF workflow (production can use server-side PDF generation)
- AI integration point: Gemini/OpenAI-compatible API can be connected to the validation endpoint in a production backend

## How AI Is Used
The prototype uses deterministic validation checks for reliable structural errors and is designed for an AI-assisted suggestion layer. In production, an LLM can normalize names, detect suspicious duplicates, classify ambiguous records, and suggest corrections. Human approval remains mandatory before certificate generation.

## Why Human Review?
AI should assist rather than silently change official participant data. CertiFlow therefore places flagged records into a review queue and requires approval/correction before generation.

## How It Works
1. Create an event and choose a certificate template.
2. Upload a CSV or load demo participant data.
3. Run AI-assisted validation.
4. Review duplicates, missing fields and invalid data.
5. Approve valid records or correct flagged records.
6. Generate certificates in bulk with unique IDs.
7. Embed a QR payload that resolves to the verification page.
8. Verify using the certificate ID or QR route.

## Run
No build step is required for the prototype.
1. Download/clone the repository.
2. Open `index.html` in a modern browser.
3. Use **Load demo data** to run the full flow immediately.
4. For real CSVs, upload a CSV with columns such as `name,email,role`.

> For a fully offline demo, download QRCode.js into the project and replace the CDN script in `index.html` with the local file.

## Production Architecture
Browser → React/Next.js frontend → Node.js/Python API → Validation service (rules + LLM) → PostgreSQL/MongoDB → Certificate/PDF service → Verification API.

## Security Considerations
- Never expose an AI API key in the browser in production.
- Keep verification records server-side.
- Use signed or random high-entropy certificate IDs.
- Validate uploaded files and enforce size/type limits.
- Rate-limit public verification endpoints.
- Audit every human approval/correction.

## Demo Credentials
No login is required for the prototype.

## Team
Solo Participant — Code Vidya Hack Day

## Selected Problem Statement
**PS 2 — Dynamic Certificate Generation & Verification Portal**
