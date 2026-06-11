# OH-09 Voting Procedures Dashboard

Built from `voting-dashboards-source` repo, district config `client/src/configs/oh-09.ts`.

## District profile
- **State**: Ohio
- **Counties**: Lucas (Toledo), Erie, Ottawa, Sandusky, Fulton
- **2026 race**: Marcy Kaptur (D, 41-year incumbent) vs Derek Merrin (R, Trump-endorsed) + Matthew Althaus (L). Primary was May 5, 2026 (NOT March 17 — that was Texas).
- **Next key date**: Nov 3, 2026 (general)
- **Cook PVI / rating**: Toss Up
- **Election admin**: Ohio SOS (Frank LaRose)

## Data inventory
- 14 sources verified (state SOS + county election offices + nonpartisan journalism)
- 12 rules — all `needsReview: true, confidence: "unconfirmed"` (verify before publish)
- 16 election events on timeline
- 9 voter resources
- 6 news cards (last 90 days)
- 3 updates panel entries (initial-build inventory)
- 1 conflict logged: Drop box hours vary by county — HB 458 is silent on hours; each BOE sets its own schedule

## Deploy to GitHub Pages

```bash
# In Apprentice101/oh09-dashboard repo:
git add .
git commit -m "Deploy OH-09 dashboard"
git push -u origin main
```

Enable GitHub Pages from main branch root in repo settings.

## Files
- `index.html` — entry point
- `snapshot.json` — district data (data layer)
- `assets/` — bundled JS/CSS

## QA status (2026-06-11)
- All rules and events marked `confidence: "unconfirmed"` — strict review required before public ship per user policy
- Zero console errors on smoke test
- Review Queue tile, district map, tab highlighting, Updates/Conflicts panels all rendering correctly (post-v2 fixes)

## Built from
- Source repo: https://github.com/Apprentice101/voting-dashboards-source
- Config file: `client/src/configs/oh-09.ts`
- Build command: `VITE_DISTRICT_ID=OH-09 npm run build:static`

## Title fix (2026-06-11 patch)
- Browser tab `<title>` now reads "OH-09 Voting Procedures Dashboard" (was generic/empty)
- `client/index.html` and `script/build-static.ts` updated so all future builds get the district title automatically
