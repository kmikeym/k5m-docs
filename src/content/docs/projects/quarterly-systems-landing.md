---
title: Quarterly Systems Landing
description: Main landing page and marketing site for Quarterly Systems
---

# Quarterly Systems Landing

The main landing page and marketing site for the Quarterly Systems platform. Features an animated timeline, product showcase, and real-time status dashboard.

## Overview

- **URL**: https://quarterly.systems
- **Tech**: Astro 5.14.1, Tailwind CSS, anime.js
- **Deploy**: Cloudflare Pages (auto-deploy on push to `main`)

## Features

### Animated Timeline
- Interactive timeline showcasing company milestones
- Smooth animations using anime.js
- Responsive design for mobile and desktop

### Apps Showcase
- Featured products grid on `/apps` page
- Links to all Quarterly Systems products
- Consistent branding across all projects

### Status Dashboard
- Real-time transparency dashboard at `/status`
- Powered by Status API Worker
- Shows GitHub activity, RSS feeds, location data
- Immutable activity history

### Admin Features
- Location tagging interface at `/admin/location`
- Activity management
- Real-time updates

## Installation

```bash
# Clone the repository
git clone [repository-url]

# Navigate to the project
cd quarterly-systems-landing

# Install dependencies
npm install

# Start development server
npm run dev  # Runs on :4321
```

## Development

### Local Development

```bash
npm run dev
```

Opens on http://localhost:4321 with hot reload.

### Building for Production

```bash
npm run build
```

Output goes to `dist/` directory.

### Deployment

Automatically deploys to Cloudflare Pages on push to `main` branch.

## Project Structure

```
quarterly-systems-landing/
├── src/
│   ├── pages/          # Astro pages
│   │   ├── index.astro # Home page
│   │   ├── apps.astro  # Products showcase
│   │   └── status.astro # Status dashboard
│   ├── components/     # Reusable components
│   └── styles/         # Global styles
├── public/             # Static assets
│   └── labs/k5m/       # Lab experiments
├── worker/             # Status API Worker
└── package.json
```

## Status API Worker

The Status API powers the real-time dashboard.

### Features
- Aggregates GitHub activity
- Fetches RSS feeds
- Tracks location data
- KV-based caching (30-minute TTL)
- Cron refresh every 10 minutes

### Deployment

```bash
cd worker
wrangler deploy
```

**API URL**: https://status-api.quarterly.systems

## Branding

- **Colors**: Purple/blue schemes
- **Typography**: Modern, clean fonts
- **Footer**: "a K5M company" attribution
- **Navigation**: Consistent across all products

## Cross-Project Integration

The landing page links to all Quarterly Systems products:
- Knowledge Base → https://base.quarterly.systems
- VibeCode → https://vibecode.quarterly.systems
- Office Communications → https://office.quarterly.systems
- Body Electric → https://body.quarterly.systems
- Vibe News → https://news.quarterly.systems
- GitHub Graph Spider → https://graph.quarterly.systems

## Key Files

- `src/pages/apps.astro` - Products showcase
- `src/pages/status.astro` - Status dashboard
- `src/pages/admin/location.astro` - Admin interface
- `worker/status-api.js` - API worker

## Contributing

1. Make changes to `src/` files
2. Test locally with `npm run dev`
3. Commit and push to `main`
4. Auto-deploys to Cloudflare Pages

---

a **K5M** company
