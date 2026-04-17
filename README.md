# Anthony's Hinge

A personal "Hinge-style" matchmaking page for Anthony Ha. Visitors can view Anthony's profile and submit their contact info if they're interested. An admin dashboard lets Anthony review all submissions.

## Files

- [anthony-profile.html](anthony-profile.html) — The public-facing profile card. Visitors browse Anthony's photos, bio, and prompts, then submit their name and contact info (phone or Instagram).
- [admin.html](admin.html) — Password-protected admin dashboard. Displays all submissions with stats, filtering by contact type, and a refresh button. Falls back to `localStorage` if the API is not configured.
- [_redirects](_redirects) — Netlify redirect rules for clean routing.

## Current State

- Hosted on Netlify
- Hero photo and 3 additional photos are live
- All prompt responses written in lowercase for a casual, friendly tone
- Submissions sent to AWS API Gateway + Lambda + DynamoDB

## Admin Access

https://lookingfortheone.netlify.app/admin.html

## Setup

### Local (no backend)
Just open `anthony-profile.html` in a browser. Submissions are saved to `localStorage` and viewable in `admin.html` using the same browser.

### With a backend (AWS)
1. Deploy an API Gateway + Lambda + DynamoDB stack to store submissions server-side.
2. In both `anthony-profile.html` and `admin.html`, set the `API_URL` constant to your actual API Gateway endpoint.

## Future Plans

- **QR Code** — Generate a QR code pointing to the hosted Netlify URL so people can scan and open Anthony's profile instantly at events or on a business card.
- **Better photo management** — Rename image files to something readable and organize them for easier swapping as photos get updated.
