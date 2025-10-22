---
title: Vibe News (FETCH)
description: AI coding news aggregator with team collaboration
---

# Vibe News (FETCH)

A collaborative news dashboard for AI and coding news, featuring shared stars, magnifications, and trash features for team-wide curation.

## Overview

- **URL**: https://news.quarterly.systems
- **API**: https://vibe-news-api.kmikeym.workers.dev
- **Tech**: Vanilla HTML/CSS/JS (frontend), Cloudflare Workers (backend), Neon PostgreSQL
- **Deploy**: Cloudflare Pages (frontend), manual deploy (worker)
- **Status**: Live

## Features

### News Aggregation
- Auto-aggregates from multiple sources
- Hacker News integration
- Dev.to articles
- RSS feed support
- Updates every 30 minutes

### Team Collaboration
- Shared stars for important articles
- Magnify interesting content
- Trash irrelevant items
- No authentication required
- Team-wide state

### Immutable Data
- Articles never deleted
- Only hidden via flags
- Complete audit trail
- Historical preservation

### Real-Time Updates
- Fresh content every 30 minutes
- Cron-based updates
- Automatic deduplication
- Smart filtering

## Installation

```bash
# Clone the repository
git clone [repository-url]

# Navigate to the project
cd "News Dashboard"
```

## Development

### Frontend Development

```bash
# Open in browser
open index.html
```

The frontend is vanilla HTML/CSS/JS - no build step required.

### Worker Development

```bash
cd worker

# Install dependencies
npm install

# Start local development
npm run dev  # Runs on :8787

# View logs
wrangler tail
```

## Deployment

### Frontend Deployment

Automatically deploys to Cloudflare Pages on push to `main`.

### Worker Deployment

Manual deployment required:

```bash
cd worker
wrangler deploy
```

## Architecture

### Frontend
- Vanilla JavaScript
- No framework dependencies
- Lightweight and fast
- Responsive design

### Backend
- Cloudflare Workers
- Neon PostgreSQL database
- Serverless architecture
- Edge computing

### Data Flow

1. Cron job triggers every 30 minutes
2. Worker fetches from sources:
   - Hacker News API
   - Dev.to API
   - Custom RSS feeds
3. Articles stored in Neon PostgreSQL
4. Frontend queries API
5. Team actions update shared state

## API Endpoints

### GET /articles
Fetch latest articles with filters:
```javascript
fetch('https://vibe-news-api.kmikeym.workers.dev/articles?limit=50')
```

### POST /star
Star an article:
```javascript
fetch('/star', {
  method: 'POST',
  body: JSON.stringify({ articleId: '123' })
})
```

### POST /magnify
Magnify an article:
```javascript
fetch('/magnify', {
  method: 'POST',
  body: JSON.stringify({ articleId: '123' })
})
```

### POST /trash
Hide an article:
```javascript
fetch('/trash', {
  method: 'POST',
  body: JSON.stringify({ articleId: '123' })
})
```

## Team Features

### No Authentication
- Open collaboration
- No login required
- Trust-based system
- Suitable for small teams

### Shared State
- Stars visible to all
- Magnified items highlighted
- Trashed items hidden
- Team-wide curation

### Collaboration Patterns
- **Star**: Important/valuable articles
- **Magnify**: Interesting for deep dive
- **Trash**: Irrelevant or low quality

## Data Sources

### Hacker News
- Top stories
- Best stories
- New stories
- Filtered for AI/coding

### Dev.to
- Popular posts
- Recent articles
- Tag-based filtering
- AI and programming focus

### RSS Feeds
- Custom feed support
- Automatic parsing
- Deduplication
- Content extraction

## Database Schema

### Articles Table
- `id`: Unique identifier
- `title`: Article title
- `url`: Article URL
- `source`: Where it came from
- `stars`: Star count
- `magnified`: Magnification status
- `trashed`: Trash flag
- `created_at`: Timestamp

### Features
- Immutable articles
- Soft deletes via flags
- Full history preservation
- Query optimization

## Configuration

### Worker Configuration

See `"News Dashboard"/worker/wrangler.toml`:
- Neon PostgreSQL connection
- Cron schedule
- Environment variables
- Route configuration

### Cron Schedule
```toml
[triggers]
crons = ["*/30 * * * *"]  # Every 30 minutes
```

## Performance

### Edge Computing
- Cloudflare Workers at the edge
- Low latency worldwide
- Automatic scaling
- High availability

### Caching Strategy
- Smart caching
- Stale-while-revalidate
- Minimal database queries
- Fast response times

## Monitoring

### Worker Logs

```bash
cd worker
wrangler tail
```

### Metrics
- Request count
- Response times
- Error rates
- Database performance

## Project Structure

```
News Dashboard/
├── index.html          # Frontend
├── styles.css          # Styles
├── app.js              # Frontend logic
└── worker/
    ├── index.js        # Worker code
    ├── wrangler.toml   # Config
    └── package.json    # Dependencies
```

## Best Practices

1. **Check regularly**: New content every 30 minutes
2. **Star valuable**: Mark important articles
3. **Magnify interesting**: Highlight for team
4. **Trash irrelevant**: Clean up noise
5. **Collaborate**: Team-wide curation

## Architecture Details

See `"News Dashboard"/CLAUDE.md` for:
- Detailed architecture
- Database schema
- API documentation
- Worker patterns

## Future Features

- Custom feeds
- User preferences (optional)
- Email digests
- Slack integration
- Mobile app

## Contributing

1. Test frontend changes locally
2. Test worker with `npm run dev`
3. Deploy worker with `wrangler deploy`
4. Push frontend to trigger auto-deploy

---

a **K5M** company
