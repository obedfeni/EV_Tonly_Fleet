# Tonly EV Fleet Management

## Setup with Supabase (Free)

### 1. Create Supabase Database
1. Go to https://supabase.com → New Project
2. Set a name and database password
3. Go to Settings → Database → Connection string → URI
4. Copy the connection string

### 2. Install & Configure
```bash
npm install
cp .env.local.example .env.local
# Fill in your Supabase URLs in .env.local
```

### 3. Push Database Schema
```bash
npx prisma db push
npm run db:seed
```

### 4. Run
```bash
npm run dev
```

## Deploy to Vercel

Set these environment variables in Vercel dashboard:
```
DATABASE_URL=postgresql://postgres:[PASSWORD]@db.XXXX.supabase.co:5432/postgres?pgbouncer=true&connection_limit=1
DIRECT_URL=postgresql://postgres:[PASSWORD]@db.XXXX.supabase.co:5432/postgres
NEXTAUTH_URL=https://your-app.vercel.app
NEXTAUTH_SECRET=generate with: openssl rand -base64 32
```

Then after first deploy, run from local:
```bash
npx prisma db push
npm run db:seed
```

## Demo Accounts (after seeding)
| Role | Email | Password |
|------|-------|----------|
| Supervisor | supervisor@tonly.com | password123 |
| Technician | tech@tonly.com | password123 |
| Worker | worker@tonly.com | password123 |
| Charging Operator | charger@tonly.com | password123 |
