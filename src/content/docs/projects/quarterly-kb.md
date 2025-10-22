---
title: QuarterlyKB
description: Knowledge base and documentation powered by Quartz
---

# QuarterlyKB

A digital garden knowledge base built with Quartz v4, featuring Obsidian-style markdown with bidirectional links and git-based versioning.

## Overview

- **URL**: https://base.quarterly.systems
- **Tech**: Quartz v4, TypeScript, Preact
- **Deploy**: Cloudflare Pages (auto-deploy on push to `v4` branch)
- **Branch**: `v4` (default branch)

## Features

### Obsidian-Style Markdown
- Write content in `content/` directory
- Use `[[Page Name]]` for internal linking
- Full Obsidian compatibility
- Markdown with frontmatter support

### Digital Garden
- Git-based dating for pages
- Automatic graph visualization
- Backlinks and forward links
- Tag-based navigation

### Modern UI
- IBM Plex Mono typography
- Dark/light mode support
- Responsive design
- Fast static site generation

## Installation

```bash
# Clone the repository
git clone [repository-url]

# Navigate to the project
cd QuarterlyKB

# Checkout v4 branch
git checkout v4

# Install dependencies
npm install
```

## Development

### Build and Serve Locally

```bash
npx quartz build --serve
```

This builds the site and starts a local server with hot reload.

### Build Only

```bash
npx quartz build
```

Output goes to `public/` directory.

## Content Management

### Adding New Pages

1. Create a markdown file in `content/` directory:
   ```bash
   # content/my-new-page.md
   ```

2. Add frontmatter:
   ```markdown
   ---
   title: My New Page
   tags:
     - documentation
     - guide
   ---

   # My New Page

   Content goes here. Link to [[Other Page]].
   ```

3. Commit and push to `v4` branch:
   ```bash
   git add content/my-new-page.md
   git commit -m "Add new page"
   git push origin v4
   ```

### Editing with Obsidian

QuarterlyKB can be edited directly in Obsidian:

1. Open the `QuarterlyKB` folder in Obsidian
2. Edit files in the `content/` directory
3. Use Obsidian's linking features
4. Commit changes via git

## Linking

### Internal Links

Use wiki-style links:
```markdown
[[Page Name]]
[[Page Name|Custom Text]]
```

### External Links

Standard markdown:
```markdown
[Link Text](https://example.com)
```

## Deployment

Automatically deploys to Cloudflare Pages when pushing to `v4` branch:

```bash
git add .
git commit -m "Update content"
git push origin v4
```

## Project Structure

```
QuarterlyKB/
├── content/            # Markdown content
│   ├── index.md       # Home page
│   ├── guides/        # Guide pages
│   └── reference/     # Reference docs
├── quartz/            # Quartz framework
├── quartz.config.ts   # Quartz configuration
└── package.json
```

## Configuration

Edit `quartz.config.ts` to customize:

- Site title and description
- Theme colors
- Navigation structure
- Plugin configuration
- Social links

## Features in Detail

### Git-Based Dating
- Automatically tracks when pages were created/modified
- Shows last updated date on each page
- Based on git history

### Graph View
- Visual representation of page relationships
- Interactive graph navigation
- Shows backlinks and connections

### Search
- Full-text search across all pages
- Fast client-side search
- Fuzzy matching

### Analytics

Uses Umami analytics:
- Privacy-focused
- No cookies
- GDPR compliant

## Content Best Practices

1. **Use descriptive titles**: Clear, concise page titles
2. **Add tags**: Organize content with relevant tags
3. **Link liberally**: Create connections between related pages
4. **Write in markdown**: Keep formatting simple and readable
5. **Commit often**: Regular commits track content evolution

## Typography

- **Font**: IBM Plex Mono
- **Style**: Modern, monospace aesthetic
- **Readability**: Optimized for technical documentation

## Branding

- Part of Quarterly Systems ecosystem
- Consistent with company branding
- "a K5M company" footer

## Contributing

1. Create content in `content/` directory
2. Use Obsidian or text editor
3. Commit to `v4` branch
4. Push triggers auto-deployment

---

a **K5M** company
