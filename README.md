# KavaWorks

A digital community platform for Pacific Island artists across the 14 nations of Te Moana-nui-a-Kiwa — the great ocean of Kiwa. Built from Pacific cultural values outward: vā, mana, inati, tautua, whanaungatanga, kaitiakitanga, fa'aaloalo.

This repository is a Next.js 15 + React 19 build of KavaWorks. It is **demo-only** — the database is a local SQLite file, there are no real payments, and auth is a stubbed current-user resolver. Every screen is seeded with plausibly-real Pacific arts ecosystem data.

## Stack

- **Next.js 15.2** (app router, React 19)
- **TypeScript 5.7**
- **Tailwind v4** (with cultural theme tokens + reduced-motion / reduced-transparency handling)
- **Drizzle ORM + better-sqlite3** (local file DB)
- **Radix UI** primitives + **Framer Motion**
- **PWA** (manifest + service worker in `public/`)

## Running locally

```bash
npm install
npm run db:push    # create the SQLite schema
npm run db:seed    # seed nations, artists, posts, market, grants, …
npm run dev        # http://localhost:3000
```

Other scripts:

| Script | What it does |
|---|---|
| `npm run build` | Next.js production build |
| `npm run start` | Run the production build |
| `npm run lint` | Next.js lint |
| `npm run db:reset` | Re-seed (alias for `db:seed`) |

## What's here

- `app/` — Next.js app router. 22 route groups across feed, discover, explore, market, drops, grants, groups, kete, events, orgs, reels, collections, playlists, messages, notifications, settings, analytics, admin, affiliate, artist profiles, and the moana / create surfaces.
- `components/` — ~60 components grouped by surface (`feed/`, `market/`, `messages/`, `reels/`, `grants/`, `cultural/`, `nav/`, `profile/`, `create/`) plus generic `ui/` primitives.
- `db/schema.ts` — Drizzle schema: nations, artists, works, posts, drops, grants, awards, groups, events, orgs, articles.
- `db/seed-data/` + `db/seed.ts` — 14 nations, 19 artist profiles, 28 posts, 16 shorts, 20 market items, 10 grants, 8 awards, 6 groups, 6 events, 8 orgs, 6 articles, 4 drops, 7 personas.
- `lib/tauhi-va-kb.ts` — cultural knowledge base (vā, attribution rules, sacred-pattern guidance, elder protocol).
- `lib/moana-ola-kb.ts` — engagement / discoverability knowledge base.
- `lib/patterns.ts` — 14 nation patterns + 5 theme patterns (texture only, never sacred motifs).
- `lib/role.ts`, `lib/auth.ts` — 7-role system (artist, audience, collector, org, adviser, elder, admin) and stubbed current-user resolver.
- `public/` — PWA manifest, service worker, app icons.
- `docs/DEMO_SCRIPT.md` — 5-minute walkthrough.
- `docs/LESSONS_LEARNED.md` — patterns to avoid in future iterations.
- `docs/image-credits.md` — every image source, credited.

## Cultural foundation

Short version: attribution is permanent, sacred patterns are texture only, elders are designated not self-declared, 95% goes to the artist, and every piece of copy carries its diacritics correctly. See `lib/tauhi-va-kb.ts` and the build brief for the full foundation.

*Tauhi vā. Hold the space. Build with respect.*
