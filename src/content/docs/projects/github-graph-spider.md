---
title: GitHub Graph Spider
description: Social graph analyzer for discovering influential developers
---

# GitHub Graph Spider

A BFS (Breadth-First Search) spider that analyzes GitHub follower/following relationships to discover "hidden influencers" in your network.

## Overview

- **URL**: https://graph.quarterly.systems (to be deployed)
- **Tech**: Vanilla HTML/CSS/JS (frontend), Cloudflare Workers (backend), D1 SQLite
- **Deploy**: Cloudflare Pages (frontend), manual deploy (worker)
- **Status**: Beta

## Features

### Social Graph Analysis
- BFS traversal of GitHub networks
- Follower/following relationship mapping
- Network visualization
- Connection discovery

### Hidden Influencer Discovery
- Find developers with high mutual connections
- Identify influential accounts you don't follow
- Network-based recommendations
- Connection strength metrics

### Background Processing
- Cron-based crawling (every 5 minutes)
- Incremental graph building
- Rate limit respecting
- Progress tracking

### D1 SQLite Storage
- Efficient graph storage
- Fast queries
- Relationship indexing
- Historical data

## Installation

```bash
# Clone the repository
git clone [repository-url]

# Navigate to the project
cd github-graph-spider
```

## Development

### Frontend Development

```bash
# Open in browser
open index.html
```

### Worker Development

```bash
cd worker

# Install dependencies
npm install

# Start local development
npm run dev  # Runs on :8787
```

## First Time Setup

### Create D1 Database

```bash
cd worker

# Create database
wrangler d1 create github-graph-db

# Execute schema
wrangler d1 execute github-graph-db --file=schema.sql

# Create .dev.vars file
cp .dev.vars.example .dev.vars
```

### Add GitHub Token

```bash
# Add to .dev.vars for local development
GITHUB_TOKEN=your_github_token_here

# Add to Cloudflare for production
wrangler secret put GITHUB_TOKEN
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

## How It Works

### 1. BFS Traversal
- Start with a GitHub username
- Fetch their followers and following
- Queue discovered users
- Repeat for each user

### 2. Relationship Storage
- Store in D1 SQLite database
- Index by user
- Track connection types
- Maintain graph structure

### 3. Recommendation Algorithm
- Count mutual connections
- Calculate recommendation scores
- Filter by thresholds
- Rank by connection strength

### 4. Background Processing
- Cron job every 5 minutes
- Process queued users
- Respect rate limits
- Update progress

## API Endpoints

### GET /spider/:username
Start crawling a GitHub user:
```javascript
fetch('/spider/kmikeym')
```

### GET /recommendations/:username
Get recommended users:
```javascript
fetch('/recommendations/kmikeym?limit=10')
```

### GET /stats
Get crawling statistics:
```javascript
fetch('/stats')
```

## Rate Limits

### GitHub API Limits
- **Authenticated**: 5,000 requests/hour
- **Unauthenticated**: 60 requests/hour
- **Respecting limits**: Built-in backoff

### Best Practices
- Use GitHub token (required)
- Respect rate limits
- Monitor usage
- Implement backoff

## Database Schema

### Users Table
```sql
CREATE TABLE users (
  username TEXT PRIMARY KEY,
  followers_count INTEGER,
  following_count INTEGER,
  crawled_at TIMESTAMP
);
```

### Relationships Table
```sql
CREATE TABLE relationships (
  from_user TEXT,
  to_user TEXT,
  type TEXT,  -- 'follows' or 'followed_by'
  PRIMARY KEY (from_user, to_user, type)
);
```

### Queue Table
```sql
CREATE TABLE queue (
  username TEXT PRIMARY KEY,
  priority INTEGER,
  added_at TIMESTAMP
);
```

## Algorithm Details

### BFS Implementation
1. Start with seed user
2. Add to queue
3. Process queue FIFO
4. For each user:
   - Fetch followers/following
   - Store relationships
   - Add new users to queue
5. Repeat until complete

### Recommendation Score
```
score = count of mutual connections
threshold = minimum connections to recommend
```

### Mutual Connections
Users who:
- You follow
- Also follow the recommended user
- Creates network connection strength

## Configuration

### Worker Configuration

Edit `wrangler.toml`:
- D1 database binding
- Cron schedule
- Environment variables
- Route configuration

### Cron Schedule
```toml
[triggers]
crons = ["*/5 * * * *"]  # Every 5 minutes
```

## Performance

### D1 SQLite
- Fast local queries
- Indexed relationships
- Efficient joins
- Low latency

### Edge Computing
- Cloudflare Workers
- Worldwide availability
- Automatic scaling
- High performance

## Monitoring

### Worker Logs

```bash
cd worker
wrangler tail
```

### Database Stats

Query D1 for statistics:
- Total users crawled
- Total relationships
- Queue depth
- Crawl progress

## Project Structure

```
github-graph-spider/
├── index.html          # Frontend
├── styles.css          # Styles
├── app.js              # Frontend logic
└── worker/
    ├── index.js        # Worker code
    ├── schema.sql      # D1 schema
    ├── wrangler.toml   # Config
    └── package.json    # Dependencies
```

## Use Cases

### Network Discovery
- Find influential developers
- Discover new connections
- Map your network
- Identify communities

### Recruitment
- Find potential candidates
- Discover talent
- Network-based hiring
- Community connections

### Community Building
- Identify community leaders
- Discover active contributors
- Build connections
- Network growth

## Privacy Considerations

- Uses public GitHub data only
- No private information
- Respects GitHub ToS
- Rate limit compliant

## Architecture Details

See `github-graph-spider/CLAUDE.md` for:
- Algorithm details
- Database schema
- API documentation
- Worker patterns

## Future Features

- Network visualization
- Community detection
- Influence metrics
- Export capabilities
- Advanced filtering

## Contributing

1. Test frontend changes locally
2. Test worker with `npm run dev`
3. Query D1 for testing
4. Deploy worker with `wrangler deploy`

## Important Notes

- **Requires GitHub token**: Must be authenticated
- **Respects rate limits**: 5,000 req/hour maximum
- **D1 database**: Must create before deploying
- **Background processing**: Cron-based, incremental

---

a **K5M** company
