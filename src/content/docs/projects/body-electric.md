---
title: The Body Electric
description: EWMA-based weight trend tracker with calorie calculations
---

# The Body Electric

An intelligent weight tracking application using Exponentially Weighted Moving Average (EWMA) to smooth daily fluctuations and reveal true trends.

## Overview

- **URL**: https://body.quarterly.systems
- **Tech**: React 18, TypeScript, Vite, Fireproof, Recharts, Tailwind CSS
- **Deploy**: Cloudflare Pages (auto-deploy on push to `main`)
- **Status**: Live

## Features

### EWMA Weight Tracking
- Smooths daily weight fluctuations
- Reveals true weight trends
- Configurable smoothing parameters
- Statistical analysis

### Calorie Delta Calculations
- Estimates calorie surplus/deficit
- Based on weight trend changes
- Helps with diet planning
- Visual feedback

### Local-First Database
- Fireproof database with IndexedDB
- All data stays on your device
- No cloud synchronization required
- Privacy-focused

### Visual Analytics
- Recharts-based visualizations
- Weight trend graphs
- Calorie delta charts
- Historical data views

## Installation

```bash
# Clone the repository
git clone [repository-url]

# Navigate to the project
cd the-body-electric

# Install dependencies (requires --legacy-peer-deps)
npm install --legacy-peer-deps

# Start development server
npm run dev  # Runs on :5173
```

## Development

### Local Development

```bash
npm run dev
```

Opens on http://localhost:5173 with hot reload.

### Building

```bash
npm run build
```

### Important Note

This project requires the `--legacy-peer-deps` flag for npm install due to dependency constraints.

## Deployment

Automatically deploys to Cloudflare Pages on push to `main` branch:

```bash
git add .
git commit -m "Update features"
git push  # Auto-deploys
```

## EWMA Algorithm

### What is EWMA?

Exponentially Weighted Moving Average (EWMA) is a statistical method that:
- Gives more weight to recent data
- Smooths out random fluctuations
- Reveals underlying trends
- Responds to actual changes

### Parameters

See `the-body-electric/CLAUDE.md` for detailed EWMA parameters and configuration.

### Benefits

- **Reduces noise**: Daily fluctuations don't affect the trend
- **Accurate trends**: See real progress, not water weight
- **Responsive**: Adapts to actual weight changes
- **Scientific**: Based on proven statistical methods

## Calorie Calculations

### How It Works

1. Track weight changes over time
2. Calculate trend using EWMA
3. Estimate calorie delta based on trend
4. Provide actionable insights

### Formulas

- Weight change → Calorie estimate
- 1 lb ≈ 3,500 calories
- Trend-based calculations
- Daily and weekly averages

## Data Privacy

### Local-First Architecture
- All data stored locally in IndexedDB
- No server uploads
- No cloud synchronization
- Complete privacy

### Data Persistence
- Fireproof database
- Automatic local storage
- Export/import capabilities
- Backup support

## Project Structure

```
the-body-electric/
├── src/
│   ├── components/     # React components
│   ├── hooks/          # Custom hooks
│   ├── utils/          # EWMA calculations
│   └── styles/         # Tailwind styles
├── public/             # Static assets
└── package.json
```

## Tech Stack Details

### React 18
- Modern React features
- Functional components
- Hooks-based architecture
- Concurrent rendering

### TypeScript
- Full type safety
- Strict mode enabled
- Type-safe calculations
- Better developer experience

### Vite
- Fast build tool
- Hot module replacement
- Optimized production builds
- Modern dev server

### Fireproof
- Local-first database
- IndexedDB storage
- Type-safe queries
- Real-time updates

### Recharts
- React charting library
- Beautiful visualizations
- Responsive charts
- Customizable themes

### Tailwind CSS
- Utility-first CSS
- Responsive design
- Dark mode support
- Custom theming

## Features in Detail

### Weight Entry
- Quick daily weight logging
- Multiple units support (lb, kg)
- Timestamp tracking
- Edit/delete entries

### Trend Visualization
- Line charts showing trends
- Raw weight vs EWMA
- Customizable time ranges
- Zoom and pan capabilities

### Calorie Insights
- Daily calorie delta
- Weekly averages
- Goal tracking
- Progress indicators

### Statistics
- Current weight
- Trend weight
- Rate of change
- Time to goal

## Configuration

Edit configuration in source files:
- EWMA parameters in utils
- Chart styling in components
- Database schema in Fireproof config
- Tailwind theme in config file

## Best Practices

1. **Weigh consistently**: Same time each day
2. **Don't panic**: Daily fluctuations are normal
3. **Trust the trend**: EWMA reveals the truth
4. **Track regularly**: More data = better trends
5. **Be patient**: Trends emerge over time

## Contributing

1. Fork the repository
2. Make changes
3. Test locally with `npm run dev`
4. Commit and push
5. Create pull request

## Architecture

See `the-body-electric/CLAUDE.md` for:
- Detailed EWMA parameters
- Database schema
- Component architecture
- State management patterns

## Future Features

- Goal setting
- Milestone tracking
- Data export
- Multiple user profiles
- Advanced analytics

---

a **K5M** company
