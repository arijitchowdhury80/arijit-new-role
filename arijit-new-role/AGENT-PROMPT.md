# PARALLEL AGENT PROMPT — Arijit New Role Proposal
## Copy-paste this entire block into a new Claude Code session to get full context.

---

You are working on **Arijit Chowdhury's internal role proposal** at Algolia. This is a polished single-page application (HTML/CSS/JS, no framework) that serves as both a **strategic vision proposal for a new role** (Director of AI Innovation & Enablement) and a **personal job application**. The audience is Algolia's new CEO (product background, week one) and CFO.

## PRIMARY FILE

```
/Users/arijitchowdhury/Library/CloudStorage/GoogleDrive-arijit.chowdhury@algolia.com/My Drive/AI/Algolia Role Proposal/algolia-ai-director-proposal-v3.1.html
```

- Local preview: `http://localhost:3000/algolia-ai-director-proposal-v3.1.html`
- GitHub: `https://github.com/arijitchowdhury80/arijit-new-role`
- Git root: `/Users/arijitchowdhury/Library/CloudStorage/GoogleDrive-arijit.chowdhury@algolia.com/My Drive/AI/Algolia Role Proposal/`

## STATUS FILE (read this first for full history)

```
/Users/arijitchowdhury/Library/CloudStorage/GoogleDrive-arijit.chowdhury@algolia.com/My Drive/AI/Algolia Role Proposal/arijit-new-role/STATUS.md
```

**READ STATUS.md BEFORE DOING ANYTHING.** It contains all decisions, all numbers, all pending work.

---

## ARCHITECTURE OVERVIEW

Single HTML file. No build step. No npm. No React. Pure HTML + CSS + vanilla JS.

**7 tabs:**
- `p-overview` — Bento grid overview (bare panel, floats on animated grid)
- `p-why` — Why this role
- `p-proof` — Why me (NEEDS: About Arijit section — blocked on photo + career history from user)
- `p-invest` — The Investment (ROI model, salary tables)
- `p-plan` — Year 1 Investment (timeline + LIVE ROI CALCULATOR)
- `p-what` — Full scope
- `p-qa` — Q&A

Tab switching: `switchTab(panelId, btn)` in JS.

---

## DESIGN SYSTEM — FOLLOW EXACTLY

**Font:** Sora only (300/400/600). Never system fonts in new content.
**Type scale:** h2=28px/300, h3=20px/400, h4=17px/600, body=16px/400
**Min font size:** 15px body text, 12px uppercase eyebrow labels. NEVER write inline font-size below 12px.

**Colors:**
- `--blue: #003DFF` (Algolia Blue)
- `--navy: #1D1F2E`
- `--teal: #0D8C6B`
- `--orange: #E8380D`
- `--text: #1D1F2E`
- `--text-muted: #5A5F7A`

**HARD RULES — NEVER BREAK:**
1. NO em dashes (—) — use hyphen (-). 152 were already removed.
2. NO emojis in body content, nav, tiles, or labels
3. Proof pills for all citations: `.proof-pill proof-pill--green/blue/amber`
4. Sora font everywhere
5. Source every stat with a URL

---

## KEY COMPONENTS THAT ALREADY EXIST

### Animated background
```javascript
initAnimatedGrid()  // Creates fixed SVG grid behind all content
```

### Bento overview tiles
```html
<div class="ov-tile ov-tile-who" data-spotlight-color="0,61,255">
  <div class="ov-q">EYEBROW LABEL</div>
  <!-- content -->
  <div class="ov-tile-nav" onclick="switchTab('p-why',null)">Link text <span>→</span></div>
</div>
```
3D tilt on hover is wired automatically by `initOverviewGrid()` JS.

### Timeline cards
```html
<div class="tl-item" style="position:relative;">
  <div class="tl-node tl-node--current">Q1</div>  <!-- or --upcoming, --horizon -->
  <div class="tl-card" style="margin-left:28px;">
    <div class="tl-card-top">
      <div><div class="tl-period">Period text</div><h3 class="tl-title">Title</h3></div>
      <span class="tl-badge tl-badge--current">Current</span>
    </div>
    <!-- content -->
    <div class="tl-progress-wrap"><div class="tl-progress-fill tl-progress-fill--current" data-progress="65"></div></div>
  </div>
</div>
```

### Salary table (interactive)
Each variable row needs: `id="row-X" data-rate="N" data-hrs="N"` on `<tr>`
Team input: `<input class="team-input" id="inp-X" type="number" value="N" oninput="calcInvestRow('X')">`
Saving cell: `<td class="r calc-saving" id="save-X">$N</td>`
Call `rebuild()` after any change to cascade all numbers.

### Proof pills
```html
<a href="URL" target="_blank" class="proof-pill proof-pill--green">
  <span class="proof-pill__badge">Source Name</span>
  <span class="proof-pill__label">Title →</span>
</a>
```

### Workstream header
```html
<div class="ws-header">
  <span class="ws-dot" style="background:var(--blue);"></span>
  <span class="ws-label" style="color:var(--blue);">WORKSTREAM TITLE</span>
</div>
```

### Productivity gain box
```html
<div class="prod-box prod-box--green">
  <div class="prod-eyebrow" style="color:#059669;">↗ Productivity Gain</div>
  <div class="prod-headline">Headline</div>
  <div class="prod-value prod-value--green" id="prod-val-X">$XXX,XXX</div>
  <p class="prod-desc">Description with source.</p>
  <div class="src-pills"><!-- proof pills here --></div>
</div>
```

---

## LIVE ROI CALCULATOR — IDs THAT MUST NOT BE BROKEN

These IDs are wired to the live calculator. If you touch them, verify the JS still works:

| ID | What it shows |
|---|---|
| `inp-ae` through `inp-vpf` | Team size inputs (16 total) |
| `save-ae` through `save-vpf` | Row saving outputs |
| `totalval-gtm/mkt/ci/prod/legal/finance` | Table totals |
| `qtotal-q1-cost`, `qtotal-q1-prod` | Q1 cost + productivity totals |
| `qtotal-q4-cost` | Q4 cost total |
| `prod-val-gtm/mkt/ci/prod` | Productivity gain values |
| `prod-hrs-gtm`, `prod-hrs-prod` | Hours redirected displays |
| `ys-cost`, `ys-prod`, `ys-roi` | Year summary values |
| `ys-total-sub` | Year summary total text |
| `ov-roi` | Overview tile ROI (8.7×) |
| `ov-value` | Overview tile combined value ($3.94M) |

---

## GIT WORKFLOW

```bash
cd "/Users/arijitchowdhury/Library/CloudStorage/GoogleDrive-arijit.chowdhury@algolia.com/My Drive/AI/Algolia Role Proposal/"
git add algolia-ai-director-proposal-v3.1.html
git commit -m "Description"
git push
```

Always commit after changes. Never leave uncommitted work.

---

## PENDING WORK (pick one of these to work on)

### PRIORITY 1 — About Arijit in Why Me tab
**Status:** BLOCKED — need photo URL and career history from Arijit
**Design:** 3-column template: career/achievements left | photo center | capabilities right
**Location to add:** Top of `id="p-proof"` panel, before the existing POC section
**When unblocked:** User will provide LinkedIn photo URL + career entries with dates

### PRIORITY 2 — Q&A tab: 3 CEO-specific questions
Add to `id="p-qa"` panel (after the existing 7 rows):
1. "How does this interact with our product AI roadmap?" — Operational AI vs product AI, different mandate, no overlap
2. "Could the Prospect Intelligence Platform become a commercial product?" — Year 2 option, SI ecosystem
3. "Is this a distraction from core business?" — Built alongside full-time partnerships role. Mandate legitimises and scales what already works.

### PRIORITY 3 — Content review
- Tighten verbose paragraphs in Why this role tab
- Q&A answers: trim to 3 sentences max each

---

## WHAT NOT TO TOUCH

- **Do not modify** v3.html, v2.html, proposal.html (older versions, for reference only)
- **Do not modify** the flywheel section (dark navy block at bottom of Year 1 tab)
- **Do not modify** the DSW modal (`id="dsw-modal"`) — it's wired to the audit table
- **Do not modify** `buildTOC()`, `switchTab()`, `scrollToToc()` — they are stable
- **Do not add emojis** to any content

---

## CONTEXT: THE PROPOSAL CASE

**The ask:** Title change to Director of AI Innovation & Enablement + $300K OTE + $150K tooling budget
**The proof:** 2 production AI systems built with zero budget (Prospect Intelligence Platform + Algolia Central), 7 completed prospect audits, $0 budget, no mandate
**The ROI:** $959K direct cost savings + $2.97M productivity/pipeline = $3.94M combined at 8.7× ROI
**The unique angle:** Algolia sells AI-native search. This role makes Algolia "Customer Zero" for the transformation it sells.
**Salary benchmarks:** 7 companies (Algolia, Coveo, Constructor, Elastic, Adobe, Salesforce, Nvidia), 8 sources, all cited in the proposal

