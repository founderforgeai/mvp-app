# MVP App - Production Ready

## Features
- 🔐 Authentication (Email + OAuth)
- 💳 Stripe Subscriptions
- 📊 Real-time Dashboard
- 🎨 Beautiful UI with TailwindCSS
- 🚀 Deploy in 5 minutes

## Quick Start

```bash
# Install dependencies
npm install

# Set up environment variables
cp .env.example .env.local
# Fill in your Supabase and Stripe keys

# Run development server
npm run dev
```

## Deployment

1. Push to GitHub
2. Connect to Vercel
3. Add environment variables
4. Deploy!

## Tech Stack
- Next.js 14 + TypeScript
- Supabase (Auth + Database)
- Stripe (Payments)
- TailwindCSS + shadcn/ui

## Database Setup

Run this SQL in Supabase:

```sql
CREATE TABLE users (
  id UUID PRIMARY KEY DEFAULT uuid_generate_v4(),
  email TEXT UNIQUE NOT NULL,
  name TEXT,
  subscription_tier TEXT DEFAULT 'free',
  created_at TIMESTAMP DEFAULT NOW()
);

CREATE TABLE subscriptions (
  id UUID PRIMARY KEY DEFAULT uuid_generate_v4(),
  user_id UUID REFERENCES users(id),
  stripe_subscription_id TEXT,
  status TEXT,
  current_period_end TIMESTAMP
);
```

## Environment Variables

See .env.example for all required variables.
