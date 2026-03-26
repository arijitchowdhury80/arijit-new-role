# Arijit New Role Proposal — Project Status
**Last updated:** 2026-03-26  
**Context:** Arijit Chowdhury (Director of Strategic Partnerships, Algolia) is pitching a net-new role: Director of AI Innovation & Enablement. Proposal is written as both a strategic vision document for the CEO/CFO AND a personal job application. Audience: new Algolia CEO (product background, week one) + CFO.

---

## FILE LOCATIONS

| Asset | Path |
|---|---|
| **Primary HTML file** | `/Users/arijitchowdhury/Library/CloudStorage/GoogleDrive-arijit.chowdhury@algolia.com/My Drive/AI/Algolia Role Proposal/algolia-ai-director-proposal-v3.1.html` |
| **Local server** | `http://localhost:3000/algolia-ai-director-proposal-v3.1.html` |
| **GitHub repo** | `https://github.com/arijitchowdhury80/arijit-new-role` |
| **Git root** | `/Users/arijitchowdhury/Library/CloudStorage/GoogleDrive-arijit.chowdhury@algolia.com/My Drive/AI/Algolia Role Proposal/` |
| **This folder** | `/Users/arijitchowdhury/Library/CloudStorage/GoogleDrive-arijit.chowdhury@algolia.com/My Drive/AI/Algolia Role Proposal/arijit-new-role/` |
| **Older versions** | Same dir: v3.html, v2.html, proposal.html (do not modify) |

---

## CURRENT TAB STRUCTURE (7 tabs)

| Tab label | Panel ID | Status | Description |
|---|---|---|---|
| **Overview** | p-overview | ✅ Complete | Bento grid: WHAT IS THE ASK / WHAT DOES IT RETURN / WHY NOW / WHAT'S THE DECISION + 3 bounce cards |
| **Why this role** | p-why | ✅ Complete | Strategic case: gap, 3 reasons now, risk of inaction, Moderna/Bain proof |
| **Why me** | p-proof | 🔶 Needs rework | POC evidence (2 systems, 7 audits, DSW modal) + 5 differentiators. PENDING: needs "About Arijit" personal intro at top (see below) |
| **The Investment** | p-invest | ✅ Complete | ROI model: merged from old Ask + Business Case. Salary benchmarks, 3-category model |
| **Year 1 Investment** | p-plan | ✅ Complete | Modern timeline + LIVE ROI CALCULATOR (all numbers dynamic, scale with team size) |
| **Full scope** | p-what | ✅ Complete | 8-dept scope with tabbed layout (Sales, Mktg, GTM, CS, Legal, Finance, R&D, HR) |
| **Q&A** | p-qa | ✅ Complete | 7 objections + 3 CEO-specific additions needed |

**CRITICAL — PENDING WORK:**
- "Why me" tab needs "About Arijit" personal introduction at the top
  - Design: 3-column with photo center (adapted from 21st.dev template)  
  - Need from Arijit: LinkedIn photo URL, career history with dates and descriptions
  - LinkedIn scraper returned partial data only (LinkedIn blocks bots)
  - Career known: Algolia (Director Strategic Partnerships), RWS/SDL (Consulting Director), Autonomy, University of London BSc Computing 1998-2002

---

## KEY NUMBERS IN THE PROPOSAL

| Metric | Value | Location |
|---|---|---|
| Investment | $450K ($300K OTE + $150K tooling) | Overview tile + Investment tab |
| Direct cost savings | $959,350/yr (dynamic — updates with calculator) | Year 1 Investment tab + Year Summary |
| Combined Year 1 value | $3.94M (dynamic) | Overview tile id="ov-value" |
| ROI | 8.7× (dynamic) | Overview tile id="ov-roi" + Year Summary id="ys-roi" |

---

## DESIGN SYSTEM — ALGOLIA BRAND (NON-NEGOTIABLE)

### Font
- **Sora** only: weights 300 (light), 400 (regular), 600 (semibold)
- Google Fonts import already in `<head>`
- Type scale: h2=28px/300, h3=20px/400, h4=17px/600, body=16px/400

### Colors
```css
--blue:      #003DFF   /* Algolia Blue — primary */
--navy:      #1D1F2E   /* Dark nav, hero bg */
--teal:      #0D8C6B   /* Secondary positive */
--orange:    #E8380D   /* Alert/risk */
--text:      #1D1F2E   /* Primary text */
--text-muted:#5A5F7A   /* Secondary text */
--text-hint: #9095A8   /* Labels/eyebrows */
--bg:        #FFFFFF
--bg-surface:#F7F7F9
--border:    rgba(29,31,46,0.10)
```

### Background
- Page: `#F8F9FB` + animated SVG grid (`initAnimatedGrid()` JS function)
- Bento tiles: `rgba(255,255,255,0.72)` glassmorphism with `backdrop-filter:blur(20px)`

### Hard rules — NEVER break these
1. **No em dashes (—) anywhere** — use hyphen (-) instead. Already replaced 152 instances.
2. **No emojis** in body content, nav, or tile labels
3. **Minimum font size**: 15px for body text, 12px for uppercase eyebrow labels
4. **Proof pills** for ALL external citations (class: `.proof-pill proof-pill--green/blue/amber`)
5. **Sora font only** — never -apple-system or other system fonts in new content

---

## KEY CSS CLASSES (use these, do not reinvent)

| Class | Use |
|---|---|
| `.panel` | Tab content wrapper (white card) |
| `.panel--bare` | Tab with no white card (Overview, Year 1 Investment) |
| `.ov-tile` | Glassmorphism bento tile |
| `.ov-bento` | 6-column bento grid container |
| `.tl-item`, `.tl-card`, `.tl-node` | Timeline item components |
| `.invest-table` | Salary/ROI data table |
| `.prod-box`, `.prod-box--green/blue` | Productivity gain callout box |
| `.ws-header`, `.ws-label` | Workstream section header |
| `.q-total-box` | Quarter total summary (dark navy) |
| `.year-summary` | Year-end ROI summary block |
| `.methodology-note` | Source acknowledgment block |
| `.method-chip`, `.method-chip--src` | Company/source chip badges |
| `.team-input`, `.team-spin` | Interactive team size input |
| `.proof-pill`, `.proof-pill--green/blue/amber` | Source citation pills |
| `.toc-item` | Right-side TOC item |
| `.pn-btn` | Pill nav button |

---

## JAVASCRIPT FUNCTIONS

| Function | Purpose |
|---|---|
| `switchTab(panelId, btn)` | Show panel, highlight nav button, rebuild TOC |
| `buildTOC(panel)` | Auto-builds right-side TOC from panel headings |
| `scrollToToc(e, id)` | Smooth scroll to TOC section |
| `calcInvestRow(rowId)` | Recalculate one salary table row |
| `spinTeam(id, delta)` | Increment/decrement team input |
| `rebuild()` | Cascade recalculate ALL tables, Q totals, year summary, Overview tile |
| `initAnimatedGrid()` | Create the animated SVG grid background |
| `initTimeline()` | Wire scroll-reveal + progress bars on timeline |
| `openDswModal()` / `closeDswModal()` | DSW pre-call brief modal |

---

## INTERACTIVE CALCULATOR — HOW IT WORKS

Every team size is a live input. Changing any number cascades:
1. Row saving = `team × hrs/wk × 50 × loaded_rate`
2. Table total = sum of variable rows + fixed amounts
3. Q1 cost total = GTM + Marketing + CI tables
4. Productivity gains scale with team size:
   - GTM pipeline: `ae_team × $150,000` (15% quota lift per AE on $1M quota)
   - Marketing output: `freed_hrs / 2080 × $130K × 2.13` (Bloomreach 113% lift)
   - CI pipeline: `ae_team × $75,000` (5% win rate per AE on $1.5M quota)
   - Product: `pm_team × $104,000` (2-week acceleration per PM)
5. Year Summary: cost savings + productivity = combined value
6. ROI = combined / $450K
7. Overview tile `id="ov-roi"` and `id="ov-value"` update instantly

**Default team sizes:** 10 AEs, 5 BDRs, 5 SEs, 3 SAs, 1 VP Sales, 1 Content Writer, 1 Social Media Mgr, 2 Marketing Mgrs, 1 DevRel, 1 VP Marketing, 1 PMM/CI Analyst, 2 Senior PMs, 1 VP Product, 1 In-House Counsel, 1 Finance Manager, 1 VP Finance

---

## SALARY RESEARCH — COMPANIES & SOURCES

Benchmarks compiled from these companies (March 2026):
**Algolia, Coveo, Constructor.io, Elastic, Adobe, Salesforce, Nvidia**

Sources: Levels.fyi, Glassdoor, RepVue, Comparably, Payscale, InhouseBlog 2026, US Bureau of Labor Statistics

Key loaded hourly rates used:
| Role | Median comp | $/hr |
|---|---|---|
| Senior AE | $285K OTE | $138 |
| BDR/SDR | $96K OTE | $46 |
| Senior SE | $248K | $119 |
| Solutions Architect | $245K | $118 |
| VP Sales | $334K | $161 |
| Content Mktg Mgr | $135K | $72 |
| Social Media Mgr | $90K | $43 |
| Marketing Manager | $145K | $70 |
| DevRel Engineer | $177K | $85 |
| VP Marketing | $384K | $185 |
| Senior PM | $264K | $127 |
| VP Product | $350K | $168 |
| In-House Counsel | $253K | $122 |
| Finance Manager | $155K | $75 |
| VP Finance | $300K | $144 |

---

## GITHUB

```bash
# Repo
https://github.com/arijitchowdhury80/arijit-new-role

# Clone (if needed)
git clone https://github.com/arijitchowdhury80/arijit-new-role.git

# Working directory
cd "/Users/arijitchowdhury/Library/CloudStorage/GoogleDrive-arijit.chowdhury@algolia.com/My Drive/AI/Algolia Role Proposal/"

# Push changes
git add algolia-ai-director-proposal-v3.1.html
git commit -m "Description of change"
git push
```

---

## WHAT'S DONE ✅

- [x] 7-tab navigation (pill nav, switchTab JS)
- [x] Animated grid background
- [x] Algolia brand applied: Sora font, colors, type scale
- [x] Overview tab: bento grid with 3D tilt animation (exact match to audit SPA)
- [x] WHY NOW tile: Strategic/Evidential/Market Urgency with proof pills
- [x] WHAT IS THE ASK tile: role, net-new badge, 4 bullet points
- [x] Why this role tab: Moderna/Bain/Shadow AI proof, qbox
- [x] Why me tab: 2 POCs, 7-audit table, DSW modal, 5 differentiators
- [x] The Investment tab: salary tables, 3-category ROI model
- [x] Year 1 Investment tab: modern timeline (Q1-Y2+) with glassmorphism cards
- [x] LIVE ROI CALCULATOR: all numbers dynamic, team size inputs, full cascade
- [x] Salary benchmarks: 7 companies, 8 sources, all cited with methodology note
- [x] Proof pills on all source citations
- [x] Right-side sticky TOC (auto-built per tab, scroll-spy)
- [x] Layout: centered content, TOC fixed right
- [x] No em dashes anywhere (152 removed)
- [x] No emojis in UI content
- [x] Source citations upgraded to proof pills
- [x] GitHub: all commits pushed, up to date

## WHAT'S PENDING 🔶

- [ ] "About Arijit" section in Why Me tab — BLOCKED on: photo URL + career history from Arijit
- [ ] Q&A tab: 3 CEO-specific questions need to be added (product roadmap, commercialization, distraction)
- [ ] The Investment tab: verify old ask cards (title/$300K OTE/$150K budget) still present at bottom of p-invest
- [ ] Content review: some verbose text still needs tightening across all tabs
- [ ] Verify all inline font sizes in newly added content meet 15px minimum (known recurring issue)

---

## DECISIONS LOG

| Decision | Rationale |
|---|---|
| 7 tabs not 8 | "The Ask" merged into "The Investment" — salary before investment framing |
| "Year 1 Investment" not "Year 1 plan" | Makes it a business case, not a roadmap |
| "The Investment" not "The Ask" | Repositions compensation as capital allocation decision |
| Salary never appears first | CFO sees $300K before ROI = instant reject. Value established first. |
| em dashes removed | "Yell AI-created" — use hyphen instead |
| Emojis removed from tiles | Same reasoning |
| Overview is bare (panel--bare) | Tiles float on animated grid like audit SPA |
| Year 1 Investment is bare | Timeline cards float on animated grid |
| Productivity gains are fully dynamic | User correctly identified hours × team = all numbers should cascade |
| ROI calc: combined / $450K | Direct cost savings ($959K) + productivity ($2.97M) = combined ($3.94M) |
| 3-5 hrs saved not 6-8 hrs | User correction: more realistic |
| Algolia Central removed from Q2 | Not relevant to Year 1 Investment tab |
| "Funding round" removed from CS triggers | CS is not prospecting — not a CS use case |
| Legal reframed as "contract review workflow" | "Too lofty" — make it practical |
| Y2+: 1 additional headcount | "3-4 is unnatural" — more realistic |
