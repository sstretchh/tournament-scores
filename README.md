# SVLA Pumpkin Classic live score hub

Live schedule, scores and standings for the SVLA Pumpkin Classic Showcase. Parents view `/`; tournament staff sign in at `/score`.

- Static pages in `public/`, serverless functions in `api/`, no build step.
- State (scores and schedule edits) is one JSON doc in a private Vercel Blob store.
- Env var `ORGANIZER_PASSCODE` is the scorekeeper passcode. Never commit it.
- Base schedule lives in `lib/schedule.js`. Staff can rename/replace/add/withdraw teams and add, move or cancel games from the Edit schedule tab.
- `lib/apply.js` and the `applyEdits` copy in `public/shared.js` must be kept in sync.
- Local dev: `STORE=file ORGANIZER_PASSCODE=test node scripts/dev-server.mjs`
