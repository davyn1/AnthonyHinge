# Anthony's Hinge

A personal "Hinge-style" matchmaking page for Anthony Ha. Visitors can view Anthony's profile and submit their contact info if they're interested. An admin dashboard lets Anthony review all submissions.

## Files

- [anthony-profile.html](anthony-profile.html) — The public-facing profile card. Visitors browse Anthony's photos, bio, and prompts, then submit their name and contact info (phone or Instagram).
- [admin.html](admin.html) — Password-protected admin dashboard. Displays all submissions with stats, filtering by contact type, and a refresh button. Falls back to `localStorage` if the API is not configured.

## Setup

### Local (no backend)
Just open `anthony-profile.html` in a browser. Submissions are saved to `localStorage` and viewable in `admin.html` using the same browser.

### With a backend (AWS)
1. Deploy an API Gateway + Lambda + DynamoDB stack to store submissions server-side.
2. In both `anthony-profile.html` and `admin.html`, replace `YOUR_API_GATEWAY_URL_HERE` with your actual API endpoint.

## Admin Access

Open `admin.html` and enter the admin password (default: `anthony2025`). Change the `ADMIN_PASSWORD` constant in `admin.html` before sharing the page.

## Future Plans

- **AWS Backend & Database** — Set up API Gateway + Lambda + DynamoDB so submissions are stored in the cloud instead of `localStorage`. This allows Anthony to view matches from any device and ensures no data is lost when the browser cache is cleared.
- **Hosting** — Deploy the site to a public URL (e.g. AWS S3 + CloudFront, or a service like Netlify/Vercel) so the profile page can be shared as a link without needing to open a local file.
- **QR Code** — Generate a QR code pointing to the hosted profile URL. Print or display it so people can scan and open Anthony's profile instantly (e.g. at events or on a business card).
