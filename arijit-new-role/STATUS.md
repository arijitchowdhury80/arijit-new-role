# Arijit New Role Proposal — Project Status
**Last updated:** 2026-03-26 (session 3)

---

## FILE LOCATIONS

| Asset | Path |
|---|---|
| **Primary HTML file** | `~/...Algolia Role Proposal/index.html` |
| **Local server** | `http://localhost:3000` (no filename needed) |
| **Live URL** | **https://arijit-new-role.vercel.app** |
| **GitHub repo** | https://github.com/arijitchowdhury80/arijit-new-role |
| **Git root** | `~/...Algolia Role Proposal/` |
| **This folder** | `~/...algolia-search-audit/arijit-new-role/` |

---

## CURRENT TAB STRUCTURE (7 tabs)

| Tab | Panel ID | Status | Notes |
|---|---|---|---|
| **Overview** | p-overview | ✅ Complete | Bento grid + bounce cards — all numbers live |
| **Why this role** | p-why | ✅ Complete | 3D accordion cards, no amber/dark gradients |
| **Why me** | p-proof | ✅ Complete | About Arijit + 2 POC bounce cards + 5 differentiators |
| **Business Case** | p-plan | ✅ Complete | Live ROI calculator, salary tables, formulas shown |
| **The Investment** | p-invest | ✅ Complete | Category A/B/C wired to calculator + ask cards |
| **Full scope** | p-what | ✅ Complete | 8-dept scope |
| **Q&A** | p-qa | ✅ Complete | 7 Q&As + 3 CEO-specific needed |

---

## LIVE CALCULATOR — DEFAULT VALUES

With default team sizes (10 AEs, 5 BDRs, 5 SEs, 3 SAs, 1 VPS, 5 marketing, 10 CSMs, 3 Renewal AEs, 2 CS Managers, 1 counsel, 1 FM, 1 VPF, 2 SPMs, 1 VPC, 1 PMM):

| Metric | Value | Element ID |
|---|---|---|
| Direct cost savings | $1,228,250/yr | ov-cost, bfc-cost, cat-b-val |
| Productivity & pipeline | $3,010,938/yr | ov-prod, bfc-prod |
| Combined Year 1 | $4,239,188 | ov-value, bfc-total |
| ROI | 9.4× | ov-roi, bfc-roi, ys-roi |

All 61 element IDs update from a single `rebuild()` call. No hardcoded values anywhere.

---

## DESIGN SYSTEM

- **Font:** Sora 300/400/600 only
- **h2:** 28px/300 | **h3:** 20px/400 | **body:** 16px/400
- **Min font size:** 15px body, 12px uppercase labels
- **Background:** #F8F9FB + animated SVG grid (20 squares, subtle)
- **Cards:** white/rgba(255,255,255,0.88), 3-layer shadow, hover lift
- **NO left borders** — Arijit specifically hates them, never use
- **NO em dashes** — removed 152 instances
- **NO emojis** in UI content

---

## SALARY RESEARCH (7 companies, 8 sources, March 2026)

Companies: Algolia, Coveo, Constructor.io, Elastic, Adobe, Salesforce, Nvidia
Sources: Levels.fyi, Glassdoor, RepVue, Comparably, Payscale, InhouseBlog, BLS, Salary.com

Key loaded rates: AE $138 · BDR $46 · SE $119 · SA $118 · VPS $161 · CMM $72 · SMM $43 · MM $70 · DRE $85 · VPM $185 · SPM $127 · VPC $168 · Counsel $122 · FM $75 · VPF $144 · CSM $73 · Renewal AE $93 · CS Manager $102

---

## WHAT'S DONE ✅

- 7-tab SPA with floating pill nav + right-side auto-TOC
- Animated grid background (GPU-accelerated)
- Overview bento grid: 3D tilt, spotlight, all values live
- Live ROI calculator: 19 inputs → cascade to 61 element IDs
- Salary tables: server-management-table card style (irc-row)
- Productivity boxes with formula display (updates live)
- Quarterly timeline: yr1-quarter containers + yr1-card project cards
- Category A/B/C cards wired to calculator
- All initial HTML values match calculator defaults (9.4× everywhere)
- Overview and Business Case show identical categories/values
- Q&A text ROI references ($4.24M) live via span IDs
- About Arijit section: photo, career, capabilities, LinkedIn link
- Source pills: 30+ clickable URLs (Glassdoor, Levels.fyi, McKinsey, etc.)
- Mobile: @media hover:none, :active states, touch JS, GPU grid
- URL: https://arijit-new-role.vercel.app (root loads directly)
- No $2.16M stale figures anywhere
- No left borders anywhere
- No emojis in UI

## WHAT'S PENDING 🔶

- [ ] Q&A: 3 CEO-specific questions (product roadmap, commercialization, distraction)
- [ ] Content tightening: Q&A answers to 3 sentences max
- [ ] About Arijit: currently uses placeholder career structure — verify dates/descriptions are accurate
- [ ] Mobile: further testing on real iPhone (user reported animations not working in session 2; partially fixed in session 3)
- [ ] The Investment tab: confirm ask cards (Title/$300K OTE/$150K budget) still display correctly

---

## KEY DECISIONS

| Decision | Rationale |
|---|---|
| OTE NOT on Overview page | Value before cost — correct persuasion sequence |
| Category A/B/C cards kept | User explicitly: never remove components, wire to calculator |
| All initial HTML = calculator defaults | Prevents visual discrepancy before JS fires |
| No left borders ever | Arijit's strongest UI preference |
| Overview + Business Case same categories | Direct cost savings / Productivity & pipeline — no split |
| Formula lines in productivity boxes | Shows verifiable math, updates with team inputs |
| Mobile: :active not :hover | iOS Safari doesn't support :hover on touch |
| $4.24M as the live combined value | Matches calculator default with all 19 team inputs |
