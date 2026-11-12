# PDF Assistant

AI-powered study tools that turn PDF documents into practice questions and quizzes.

## Current features
- Responsive landing page
- PDF upload endpoint (10 MB limit)
- Server-side PDF text extraction
- AI-generated multiple-choice questions
- Basic request rate limiting and security headers
- API key stays on the server; it is never sent to the browser

## Run locally
1. Install Node.js 18.17 or newer.
2. Run `npm install`.
3. Set the `OPENAI_API_KEY` environment variable on your server.
4. Run `npm start`.
5. Open `http://localhost:3000`.

Never put your API key in `index.html`, commit it to GitHub, or share it in chat.

## API
- `GET /api/health` — checks whether the server and AI configuration are available.
- `POST /api/generate` — multipart form with `pdf` and optional `count` (3–15).

## Current limitations
- Scanned/image-only PDFs need OCR and are not supported yet.
- Authentication, per-user usage quotas, billing, persistent accounts, and weekly active-user analytics are not implemented yet.
- Uploaded PDF bytes are processed in memory and are not intentionally saved to disk. Avoid uploading sensitive documents until the production privacy and retention setup has been reviewed.
- Add a production hosting provider and configure `OPENAI_API_KEY` as a private environment variable before public launch.

## Roadmap
1. Authentication and user accounts.
2. Free-plan quotas and premium subscriptions.
3. Admin dashboard with weekly active-user counts.
4. OCR for scanned PDFs.
5. Automated tests, deployment, privacy policy, and monitoring.
