# PENDING — Task Queue
# STATUS OPTIONS: [ ] = open · [CLAIMED yyyy-mm-dd Agent] = in progress · [DONE yyyy-mm-dd] = complete
# RULE: Claim a task BEFORE starting it. Complete it and mark DONE when pushed to git.

---

## PRIORITY: HIGH

- [CLAIMED 2026-03-26 Primary] About Arijit section in Why Me tab
  - Insert above existing POC content in `id="p-proof"` panel
  - Design: 3-column (career left | photo center | capabilities right) adapted from 21st.dev template
  - BLOCKED: Need from Arijit: LinkedIn photo URL + career history (roles, companies, dates, 2-3 sentences each)
  - Career known so far: Algolia Director Strategic Partnerships, RWS/SDL Consulting Director, Autonomy, University of London BSc Computing 1998-2002
  - When Arijit provides photo + career → unblock and build

- [ ] Q&A tab: Add 3 CEO-specific questions
  - Location: `id="p-qa"` after the existing 7 `.row` divs
  - Q1: "How does this interact with our product AI roadmap?" → Operational AI vs product AI, different mandate
  - Q2: "Could the Prospect Intelligence Platform become a commercial product?" → Year 2 option, SI ecosystem
  - Q3: "Is this a distraction from the core business?" → Built alongside full-time role. Mandate legitimises what already works.
  - Priority: HIGH · Blocked on: nothing

---

## PRIORITY: MEDIUM

- [ ] The Investment tab: verify ask cards still present
  - Confirm that `id="p-invest"` still shows the 3 ask cards (Title / $300K OTE / $150K budget) at the bottom
  - The merge from old Ask + Business Case may have displaced them
  - Action: scroll to bottom of p-invest and verify

- [ ] Content review: Why this role tab
  - Moderna box paragraph 2 can be cut (repeats paragraph 1)
  - Some risk rows are verbose — trim to 2 sentences max
  - Bain box: verify paragraph order (paragraph 2 "This is Algolia today..." should come first)

- [ ] Q&A answers: trim to 3 sentences max each
  - Currently some answers are 4-6 sentences
  - A CEO scanning wants crisp, not thorough

- [ ] Verify all fonts in Year 1 Investment tab content
  - New content added by agent — check all inline font-size values are ≥15px for body text
  - Check: methodology note, productivity boxes, workstream headers, year summary

---

## PRIORITY: LOW

- [ ] "Full scope" tab header
  - Currently shows "What it does" content without a strong intro
  - Add 1-sentence charter statement at top

- [ ] Overview: WHAT IS THE ASK tile
  - Consider whether "Net-new role - does not exist today" badge needs more context
  - Possibly add "Reports to: CEDO (current structure unchanged)"

---

## DONE

- [DONE 2026-03-26] Build 7-tab SPA from scratch
- [DONE 2026-03-26] Apply Algolia brand: Sora font, colors, type scale
- [DONE 2026-03-26] Animated grid background
- [DONE 2026-03-26] Overview bento tiles with 3D tilt animation
- [DONE 2026-03-26] Floating pill nav
- [DONE 2026-03-26] Right-side sticky TOC
- [DONE 2026-03-26] Modern timeline for Year 1
- [DONE 2026-03-26] Live ROI calculator (all 16 inputs, full cascade)
- [DONE 2026-03-26] Salary research: 7 companies, 8 sources
- [DONE 2026-03-26] Salary tables with loaded hourly rates in each initiative
- [DONE 2026-03-26] Productivity gains dynamic (scale with team size)
- [DONE 2026-03-26] Remove all em dashes (152)
- [DONE 2026-03-26] Remove emojis from UI
- [DONE 2026-03-26] Proof pills on all citations
- [DONE 2026-03-26] Fix layout: centered content, TOC fixed right
- [DONE 2026-03-26] WHY NOW tile: reworded 3 triggers for CEO audience
- [DONE 2026-03-26] Source methodology acknowledgment block
- [DONE 2026-03-26] /persist command created
