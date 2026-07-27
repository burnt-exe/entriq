# Entriq

Entriq is a GitHub-native prototype for a multi-tenant digital raffle SaaS platform designed for South African schools, charities, NGOs, sports clubs and community organisations.

## Current implementation

The repository contains a responsive static front-end that runs directly on GitHub Pages without Replit-specific packages or runtime services:

- Public marketing landing page
- Raffle discovery and search
- Raffle details and demo checkout
- Login and registration wireframes
- Raffle provider dashboard
- Ticket holder dashboard
- Platform administrator dashboard
- Responsive WCAG-oriented design system
- South African compliance, POPIA, NLC and SGB workflow messaging
- GitHub Actions deployment workflow

## Local preview

Because the current prototype is static, it can be served with any local HTTP server:

```bash
python -m http.server 8080
```

Open `http://localhost:8080`.

## GitHub Pages

The workflow in `.github/workflows/pages.yml` deploys the repository root to GitHub Pages whenever `main` is updated. In repository settings, set **Pages → Source** to **GitHub Actions** if it is not already configured.

## Production architecture

GitHub Pages only hosts static assets. A production raffle platform requires independently deployed backend services. Recommended architecture:

- Frontend: React/Next.js or a progressive web application
- API: Node.js/TypeScript service behind an API gateway
- Identity: Microsoft Entra External ID, Auth0, Clerk or equivalent
- Database: managed PostgreSQL with tenant isolation and encrypted backups
- Payments: South African-capable payment service provider approved for the operating model
- Object storage: compliance documents, invoices and draw evidence
- Notifications: email, SMS and WhatsApp providers
- Audit: append-only security and financial event store
- Hosting: Azure, AWS, Google Cloud or another controlled production environment

Do not place payment secrets, OAuth client secrets, database credentials or administrative keys in the GitHub Pages application.

## Compliance status

This code is a product prototype, not legal authorisation to operate a raffle. Each operator must obtain the required legal, regulatory, governance, privacy, payment-provider and financial approvals before ticket sales begin.
