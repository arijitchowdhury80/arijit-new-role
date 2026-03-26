# CHANGELOG — Append-only work log
# RULE: Add new entries at the TOP. Never modify existing entries below your new one.

---

## [2026-03-26 02:30] — Session by Primary Agent (session 2)

### What was done this session
- Business Case tab: removed comparison table + flywheel (redundant with salary data and quarterly timeline)
- Business Case tab: bounce-card financial summary built at top (3 cards: cost savings / productivity / ROI)
- Business Case tab: all 30 source pills made clickable with real URLs (Glassdoor, Levels.fyi, RepVue, McKinsey, Salesforce, Gainsight, Bain, Clari, Thomson Reuters, Gartner)
- Business Case tab: footnote restructured as 2-row inline line — not a box, not a card
- Business Case tab: company chips in footnote link to actual salary pages
- Business Case tab: quarter containers converted to white (#FAFBFC) with 3-layer shadow (no colour tint)
- Business Case tab: mini bounce cards (2-card) at top of each quarter with clickable source pills
- Business Case tab: quarterly timeline restored after accidental deletion in cleanup pass
- Overview page: third bounce card ("THE INVESTMENT" / $2.16M hardcoded) removed — redundant with tile 2
- Overview page: proof row now 2 cards (Prospect Intelligence + Algolia Central) filling width equally
- Animation slowed: 45→20 squares, MAX_OP 0.55→0.22, frequency halved
- Fixed critical layout bug: bfc-grid div was unclosed — everything below cards was squished into grid column
- All width constraints removed from p-plan panel — content fills full content area
- Added Q2/Q3/Q4 quarterly total IDs to rebuild() — all 8 mini cards now live
- CS salary research: CSM $73/hr, Renewal AE $93/hr, CS Manager $102/hr — all verified
- CS table added to Q3 timeline card, wired into live calculator (10 CSMs, 3 Renewal AEs, 2 Managers)

### Files modified
- algolia-ai-director-proposal-v3.1.html — primary proposal (major changes)
- arijit-new-role/CHANGELOG.md — this file

### Numbers (current live state with default team sizes)
- ROI: 9.4× (dynamic)
- Combined value: $4.24M (dynamic)
- Direct cost savings: $1,228,250 (dynamic)
- Productivity gains: $3,010,938 (dynamic)
- Investment: $450K (fixed)
- 30 clickable source pills across all bounce cards

### Decisions made
- DECIDED: Remove comparison table — redundant with salary benchmarks already shown inline
- DECIDED: Remove flywheel — redundant with quarterly timeline progression
- DECIDED: Remove third Overview proof card (THE INVESTMENT) — stale hardcoded number, redundant with tile 2
- DECIDED: Two POC cards > three cards. Cleaner, more focused message.
- DECIDED: Quarter backgrounds = white (#FAFBFC) with shadow — no colour tint competing with animated grid
- DECIDED: Methodology = inline footnote line (not a box) — substantiated but not highlighted
- DECIDED: All source references must be real clickable URLs — zero unverifiable claims

---

## [2026-03-26 01:15] — Session by Primary Agent (initial setup)

### What was done this session
- Built full proposal from scratch: single HTML file, 7-tab SPA
- Applied Algolia brand: Sora font, brand colors, animated grid background
- Built Overview tab: bento grid with 4 glassmorphism tiles + 3 bounce cards
- Built floating pill nav (matches audit SPA)
- Built right-side sticky TOC (auto-builds per tab, scroll-spy)
- Built modern timeline for Year 1 Investment tab: Q1-Y2+ with glassmorphism cards
- Built LIVE ROI CALCULATOR: all 19 team size inputs, full cascade recalculation
  - Cost savings, productivity gains, pipeline gains all scale with team size
  - Overview tile (ov-roi, ov-value) updates in real time
- Conducted salary research: 7 companies, 8 sources, March 2026
- Added Adobe, Salesforce, Nvidia salary data (extended research)
- Added SE/SA/CSM/Renewal AE/VP roles to salary benchmarks
- Populated salary tables in each initiative card with verified benchmarks
- Sourced productivity multipliers: Salesforce, Bloomreach, Klue, McKinsey, P&G, Gainsight, Bain, Clari
- Removed all 152 em dashes from document
- Removed all emojis from UI content
- Applied proof pills to all source citations
- Applied server-management-table card style to all salary tables (7 tables)
- Built quarterly timeline with quarter containers (yr1-quarter) and project cards (yr1-card)
- 3 parallel agents ran table conversion (Q1/Q2+Q3/Q4) in ~4 minutes
- Business Case tab renamed from Year 1 plan/Investment
- Navigation reduced to 7 tabs from 8

---
