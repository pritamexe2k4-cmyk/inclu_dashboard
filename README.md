# IncluHub Dashboard

Role-based education ops app for **Admin**, **Educator**, and **Student** portals (IncluHub creative education school). Server actions and Supabase RLS protect workflows.

## Why

Replace sheet-based school ops with institutes, teams, stages, portfolio review, and studio check-in — real operational tool used in IncluHub workflows.

## Stack

- Next.js 16 · React 19 · TypeScript
- Tailwind CSS · shadcn-style UI
- Supabase (Postgres, Auth, RLS, Storage, RPC)
- Vercel deploy target

## Run

```bash
git clone https://github.com/pritamexe2k4-cmyk/inclu_dashboard.git
cd inclu_dashboard
npm install
cp .env.example .env.local   # set Supabase + APP_URL vars; never commit secrets
npm run dev
```

Open http://localhost:3000. Admin creates users — no public signup.

### Branches

| Branch | Use |
|--------|-----|
| `master` | Package F baseline (migrations `001`–`013`) |
| `feat/local-dev` | Founder workflows (also `014`–`022`) |

Apply SQL migrations in order from `supabase/migrations/` (see [supabase/README.md](supabase/README.md)).

### Verify

```bash
npm exec tsc -- --noEmit --incremental false
npm run lint
npm run build
npm run test:release-authz
```

## Status

Package F (Stages 1–4) on `master`. Founder flows on `feat/local-dev` add notifications, QR check-in, broadcast, and Stage 5 messaging.

Docs: [docs/README.md](docs/README.md) · [AGENTS.md](AGENTS.md)
