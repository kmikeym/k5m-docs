---
title: Water Tracker
description: Local-first hydration tracking application
---

# Water Tracker

A local-first water intake tracking application to help you stay hydrated throughout the day. Available as a web app, desktop application, and CLI tool.

## Overview

Water Tracker helps you maintain healthy hydration habits with:

- 💧 Track daily water intake in ounces
- 📊 Visual progress indicators
- 🔥 Daily streak tracking
- 🎯 Customizable daily goals
- 💾 Local data storage (no cloud required)

## Installation

```bash
# Clone the repository
git clone https://github.com/kmikeym/water

# Navigate to the project
cd water

# Install dependencies
bun install
```

## Usage

### Web App

Start the development server:

```bash
bun run dev
```

Then open http://localhost:3000 in your browser.

### Desktop App

Launch the Electron-based desktop application:

```bash
bun run dev:desktop
```

Or build a standalone executable:

```bash
bun run build:desktop
```

### CLI Tool

Build the CLI executable:

```bash
bun run build:cli
```

Use the CLI commands:

```bash
# Add water intake
./water add 16

# Check today's status
./water status

# View history
./water history

# Set daily goal
./water goal 80

# Show help
./water help
```

## Features

### Quick Add Buttons

Tap to quickly add common amounts:
- 8 oz (Glass)
- 12 oz (Small Bottle)
- 16 oz (Water Bottle)
- 20 oz (Large Bottle)

### Progress Tracking

- Circular progress indicator
- Percentage of daily goal
- Color changes when goal is reached
- Celebration animation on goal completion

### History & Entries

- Timestamped entries
- Delete individual entries
- Reset daily data
- View past 14 days

### Streak System

- Track consecutive days meeting your goal
- Visual calendar showing completed days
- Motivational streak counter

## Data Storage

- **Web App**: Browser localStorage
- **Desktop App**: Electron localStorage
- **CLI**: `~/.water-tracker/data.json`

Web and Desktop apps share data. CLI uses a separate file for portability.

## Tech Stack

- **Runtime**: Bun
- **Language**: TypeScript
- **Web**: Vanilla HTML/CSS/JS
- **Desktop**: Electron
- **CLI**: Compiled Bun executable

## Project Structure

```
water/
├── index.html          # Web app HTML
├── styles.css          # Styles
├── app.ts              # Web app logic
├── index.ts            # Bun server
├── cli.ts              # CLI app
├── water               # CLI executable
├── electron-main.js    # Electron main process
├── electron-preload.js # Electron preload
└── package.json        # Config
```

## Contributing

Contributions are welcome! Please:

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## License

Open source - see repository for details.

---

a **K5M** company
