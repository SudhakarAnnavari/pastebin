1️⃣ Deployed URL

This is the live link where your app is running.
Since you deployed on Vercel, it will be something like:

https://pastebin-flax-six.vercel.app


Make sure:

/ shows your UI to create a paste.

/p/<id> works and shows the paste content.

/api/pastes and /api/pastes/<id> work with proper JSON responses.

Health check works: /api/healthz → returns { "ok": true }.

2️⃣ Git repository URL

Make sure your repository is public (or accessible to whoever is grading).
Example:

https://github.com/velicharlasrilekha/pastebin.git


Check:

All source code is committed (app/, lib/, components/, etc.)

No secrets (Redis URL/token) are committed.

README.md exists at the root.

3️⃣ README.md content

Create a short README (1–2 pages max) that explains:

Example:
# Pastebin-Lite

A lightweight Pastebin clone built with Next.js and Redis. Users can create text pastes, receive a shareable link, and view them with optional TTL (expiry) and max view limits.

## Features

- Create a paste with arbitrary text
- Optional time-based expiry (TTL)
- Optional view-count limit
- REST APIs for paste creation and retrieval
- HTML page to view paste content safely
- Deterministic expiry testing via `x-test-now-ms` header

## Persistence Layer

- Redis (Upstash) used for persistence
- Ensures pastes survive serverless deployments

## Running Locally

1. Clone the repository:
   ```bash
   git clone https://github.com/SudhakarAnnavari/pastebin-lite.git
   cd pastebin-lite


Install dependencies:

npm install


Add environment variables in .env.local:

REDIS_URL=<your_upstash_redis_url>
REDIS_TOKEN=<your_upstash_redis_token>
NEXT_PUBLIC_BASE_URL=http://localhost:3000
TEST_MODE=1


Run the development server:

npm run dev


Open http://localhost:3000

Deployment

Deployed on Vercel: https://pastebin-flax-six.vercel.app

Design Decisions

Next.js App Router for server-side rendering of paste pages

Redis (Upstash) for persistent key-value storage

TTL and max views handled atomically in Redis

UI built with Tailwind CSS, simple and clean

Added export const runtime = "nodejs" for serverless Redis support