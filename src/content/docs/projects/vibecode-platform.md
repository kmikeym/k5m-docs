---
title: VibeCode Platform
description: No-code/low-code rapid application development platform
---

# VibeCode Platform

A no-code/low-code platform for rapid application development, forked from the open-source vibes.diy project.

## Overview

- **URL**: https://vibecode.quarterly.systems
- **Tech**: React, TypeScript, Fireproof, pnpm monorepo
- **Upstream**: https://github.com/VibesDIY/vibes.diy
- **Public Demo**: https://vibes.diy
- **Status**: Beta

## Features

### No-Code/Low-Code Development
- Visual application builder
- Drag-and-drop interface
- Rapid prototyping
- Real-time preview

### Fireproof Database
- Local-first data storage
- Automatic synchronization
- Offline-first architecture
- Built-in encryption

### Monorepo Architecture
Multiple packages:
- `vibes.diy` - Core platform
- `call-ai` - AI integration
- `use-vibes` - React hooks
- `prompts` - Prompt templates

## Installation

```bash
# Clone the repository
git clone [repository-url]

# Navigate to the project
cd vibecoder

# Install dependencies (uses pnpm)
pnpm install
```

## Development

### Start Dev Server

```bash
pnpm dev
```

### Run All Checks

Before committing, run the full check suite:

```bash
pnpm check
```

This runs:
- Format checking
- Build process
- Tests
- Linting

## Code Standards

### TypeScript Requirements
- **Strict TypeScript**: No `any` types allowed
- Full type coverage
- Type-safe APIs
- Comprehensive type definitions

### Best Practices
- See `vibecoder/CLAUDE.md` for detailed practices
- Follow React best practices
- Use functional components
- Implement proper error handling

## Monorepo Structure

```
vibecoder/
├── packages/
│   ├── vibes.diy/     # Core platform
│   ├── call-ai/       # AI integration
│   ├── use-vibes/     # React hooks
│   └── prompts/       # Prompt templates
├── .github/           # CI/CD workflows
└── package.json       # Monorepo config
```

## Deployment

Deployment is handled by GitHub Actions on tag push:

```bash
# Create and push a tag
git tag v1.0.0
git push origin v1.0.0
```

Deploys to Vercel/Netlify automatically.

## Upstream Synchronization

This is a fork of vibes.diy and may need periodic syncing:

```bash
# Add upstream remote (once)
git remote add upstream https://github.com/VibesDIY/vibes.diy

# Fetch upstream changes
git fetch upstream

# Merge upstream changes
git merge upstream/main
```

## Key Features

### AI Integration
- Built-in AI capabilities via `call-ai` package
- Prompt management
- AI-assisted development
- Smart code generation

### React Hooks
- Custom hooks in `use-vibes` package
- Reusable logic
- State management
- Side effects handling

### Local-First Architecture
- Fireproof database
- Offline functionality
- Automatic sync when online
- No server required for basic usage

## Development Workflow

1. **Make changes** in appropriate package
2. **Test locally** with `pnpm dev`
3. **Run checks** with `pnpm check`
4. **Commit changes** following conventional commits
5. **Push to main** or create PR
6. **Tag for release** when ready to deploy

## Package Details

### vibes.diy
Core platform with UI components and application logic.

### call-ai
AI integration package for intelligent features:
- LLM integration
- Prompt management
- Response handling

### use-vibes
React hooks for common patterns:
- Data fetching
- State management
- Side effects
- Custom hooks

### prompts
Prompt templates and management:
- Pre-built prompts
- Prompt chaining
- Template system

## Contributing

1. Read `vibecoder/CLAUDE.md` for detailed guidelines
2. Use strict TypeScript (no `any`)
3. Run `pnpm check` before committing
4. Follow React best practices
5. Write tests for new features

## Configuration

Edit package-specific configuration files:
- `tsconfig.json` - TypeScript settings
- `vite.config.ts` - Build configuration
- `.eslintrc` - Linting rules
- `package.json` - Dependencies and scripts

## Platform Capabilities

### Application Types
- Web applications
- Mobile-responsive apps
- Progressive Web Apps (PWAs)
- Single Page Applications (SPAs)

### Integration Options
- API connections
- Database integration
- Third-party services
- Custom backends

## Future Development

- Enhanced AI features
- More UI components
- Better templates
- Improved documentation
- Community plugins

## Resources

- **Upstream Project**: https://github.com/VibesDIY/vibes.diy
- **Public Demo**: https://vibes.diy
- **Documentation**: See individual package READMEs

---

a **K5M** company
