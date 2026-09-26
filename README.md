# JUMLSA Web App

A lightweight, single-file web app for the Jimma University Medical Laboratory Students Association (JUMLSA) — landing page, about/mission/vision, mentorship overview, membership fees, program announcements, a registration form with bank-screenshot upload, and a host/admin panel.

Built with plain **HTML, CSS, and JavaScript** — no framework, no build step, no server required.

## Files

- `index.html` — the entire app (deploy this as-is).

## Deploying

This is a static site, so it can be hosted anywhere that serves static files:

- **Vercel / Netlify / GitHub Pages**: upload the zip or connect the repo; make sure the file is named `index.html` at the project root (already done).
- **Any web server**: drop `index.html` into the web root.

No build command or environment variables are needed.

## Before you launch — update these placeholders

Open `index.html` and search for:

- `[Insert CBE account number & name here]` — replace with your real CBE account details.
- `[Insert EMLA account number here]` — replace with the real EMLA account details.

Also consider changing the **admin password**, currently set in the script as:

```js
if(pass==='jumlsa2026'){ ... }
```

## How it works

- **Registration form**: students fill in their details and optionally upload a screenshot of their 300 ETB bank transfer as proof of payment. After submitting, they get a button to notify the host on Telegram (`@Ttrrrkk`) with a copyable message, since this app has no backend to receive submissions automatically across devices.
- **Announcements**: the host can post program announcements from the admin panel; a notification bell badge shows unread announcements to visitors.
- **Admin panel**: accessible via the "Host / admin login" link in the footer (password-protected). From there the host can post announcements, view registrations submitted on that device, mark payment status (pending / paid - approved / rejected), and copy the registration list.

## Important limitation: local storage only

This app stores all data (announcements and registrations) in the browser's `localStorage` — there is no shared database or backend. That means:

- Data only persists on the **same device/browser** where it was entered.
- A registration a student submits on their phone will **not** automatically appear in the admin panel on your computer.
- This is why every registration also prompts the student to notify you on Telegram — that's the reliable, cross-device way you'll actually receive submissions and payment screenshots.

If you'd like real-time, shared, cross-device data (e.g. one live roster everyone including you can see), that requires adding a real backend (such as Firebase or a small server) — let me know if you'd like that built out.
