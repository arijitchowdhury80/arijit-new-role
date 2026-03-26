# CHANGELOG — Append-only work log
# RULE: Add new entries at the TOP. Never modify existing entries below your new one.

---

## [2026-03-26 06:00] — Session by Primary Agent (session 3 — consistency + polish)

### What was done this session

**ROI Consistency fixes:**
- Fixed stale Category A/B/C hardcoded values ($729K/$1.29M/$135K) — wired to live calculator
  - Cat A = P.gtm + P.ci (revenue pipeline), Cat B = totalCost, Cat C = P.mkt + P.pm + P.cs
- Fixed Overview tile initial HTML values — were stale from before CS was added:
  - ov-cost: $959K → $1,228,250 | ov-prod: $2.97M → $3,010,938 | ov-roi: 8.7× → 9.4× | ov-value: $3.94M → $4.24M
- All initial HTML values now match exact calculated defaults (verified with Python formula)
- Q&A text references ($3.94M mentions) made live via span IDs updated by rebuild()
- Removed stale $2.16M references from Q&A and comparison text (updated to $3.94M → now $4.24M)

**Calculated correct defaults (with default team inputs):**
- totalCost = $1,228,250/yr | totalProd = $3,010,938/yr | combined = $4,239,188 | ROI = 9.4×

**UI improvements:**
- Decision tile: removed Owner/Timeline → replaced with 3 approval bullets (role, tooling budget)
- Removed compensation bullet from decision tile — appears in Investment tab
- Business Case: restored Category A/B/C cards (were accidentally deleted) and wired to calculator
- Productivity boxes: added formula display under each value (shows the math, updates dynamically)
- Business Case bounce cards + Overview tile now show identical category names and values
- Removed duplicate `algolia-role-proposal` Vercel project → only arijit-new-role.vercel.app remains

**URL / deployment:**
- Renamed HTML to index.html → loads at root: https://arijit-new-role.vercel.app
- Set Vercel alias: arijit-new-role.vercel.app
- Removed duplicate algolia-role-proposal Vercel project

**Mobile responsive:**
- Added @media (hover: none) CSS → :active states replace :hover on iOS Safari
- Bounce card panels auto-show on touch devices (CSS, no JS needed)
- Touch JS wrapped in DOMContentLoaded (fixed timing bug)
- Animated grid GPU-accelerated with will-change + translateZ(0)

**Content fixes:**
- All em dashes verified gone
- No emojis in UI content
- OTE left out of Overview tile (deliberate — value before cost sequencing)
- Formula lines in productivity boxes show: team × rate × formula = result

### Numbers (final state with default team sizes)
- ROI: 9.4× | Combined: $4.24M | Cost savings: $1,228,250 | Productivity: $3,010,938
- Investment: $450K (fixed) | OTE: $300K (fixed, appears in Investment tab only)

### Decisions made
- DECIDED: OTE stays out of Overview page — correct persuasion sequence (value before cost)
- DECIDED: All hardcoded initial HTML values must match calculator defaults exactly
- DECIDED: Category A/B/C cards stay — wired to calculator, not removed
- DECIDED: Overview tile shows same two categories as Business Case (no separate revenue row)
- DECIDED: Formula lines under each productivity value — shows verifiable math

### Files modified
- index.html (primary proposal — every change committed to GitHub)
- arijit-new-role/CHANGELOG.md, STATUS.md, PENDING.md

---

## [2026-03-26 02:30] — Session by Primary Agent (session 2)

### What was done this session
- Business Case tab: removed comparison table + flywheel (redundant)
- Business Case tab: bounce-card financial summary at top (3 cards: cost/productivity/ROI)
- All 30 source pills made clickable with real URLs
- Salary footnote restructured as 2-row inline line
- Quarter containers: white (#FAFBFC) with shadow
- Mini bounce cards per quarter with clickable source pills
- Timeline restored after accidental deletion
- Overview: third bounce card ("THE INVESTMENT") removed — redundant with tile 2
- Animation: 45→20 squares, MAX_OP 0.55→0.22, frequency halved
- Fixed bfc-grid unclosed div — was squishing content into narrow column
- Q2/Q3/Q4 quarterly total IDs added to rebuild()
- CS salary research: CSM $73/hr, Renewal AE $93/hr, CS Manager $102/hr
- CS table wired into live calculator (10 CSMs, 3 Renewal AEs, 2 Managers)

---

## [2026-03-26 01:15] — Session by Primary Agent (session 1 — initial build)

### What was done this session
- Built full proposal from scratch: single HTML file, 7-tab SPA
- Applied Algolia brand: Sora font, brand colors, animated grid background
- Built Overview tab: bento grid with 4 glassmorphism tiles + bounce cards
- Built floating pill nav, right-side sticky TOC
- Built modern timeline for Business Case tab: Q1-Y2+ with glassmorphism cards
- Built LIVE ROI CALCULATOR: all 19 team size inputs, full cascade
- Salary research: 7 companies + Adobe/Salesforce/Nvidia, 8 sources, March 2026
- All salary tables: server-management-table card style (irc-row)
- Quarterly timeline: yr1-quarter containers + yr1-card project cards
- 3 parallel agents ran table conversion in ~4 minutes
- Navigation: 7 tabs
- /persist command created

---
