# Allign Transcribe

Cloud-based transcription SaaS that converts audio and video files into text efficiently and affordably.

## Tech Stack

- **Frontend**: Next.js 14 (App Router) + TypeScript + shadcn/ui
- **Backend**: Node.js worker on Fly.io
- **Database**: Supabase (Postgres + Storage + Auth)
- **Payments**: Stripe
- **Transcription**: OpenAI Whisper API
- **Email**: Resend

## Project Structure

```
allign-transcribe/
├── app/         # Next.js frontend (deploys to Vercel)
├── worker/      # Node.js worker (deploys to Fly.io)
├── supabase/    # Database migrations and seed data
└── shared/      # Shared TypeScript types and constants
```

## Getting Started

### Prerequisites

- Node.js 20+
- Supabase account
- OpenAI API key
- Stripe account
- Resend account
- Fly.io CLI (for worker deployment)

### Local Development

1. Clone the repository:
```bash
git clone https://github.com/loaitaha/allign-transcribe.git
cd allign-transcribe
```

2. Install dependencies:
```bash
npm install
```

3. Setup environment variables:
```bash
# Copy example env files
cp app/.env.example app/.env.local
cp worker/.env.example worker/.env
```

4. Run Supabase migrations (see `supabase/README.md`)

5. Start development servers:
```bash
# Terminal 1 - Frontend
npm run dev:app

# Terminal 2 - Worker
npm run dev:worker
```

## Deployment

### Frontend (Vercel)
```bash
cd app
vercel
```

### Worker (Fly.io)
```bash
cd worker
flyctl deploy
```

## Documentation

- [Architecture Overview](./docs/architecture.md)
- [Database Schema](./supabase/README.md)
- [API Reference](./docs/api.md)
- [Credit System](./docs/credits.md)

## License

Proprietary - All rights reserved
