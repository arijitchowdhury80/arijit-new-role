# CHANGELOG — Append-only work log
# RULE: Add new entries at the TOP. Never modify existing entries below your new one.
# FORMAT: ## [DATE TIME] — Session by [agent name]

---

## [2026-03-26 01:15] — Session by Primary Agent (initial setup)

### What was done this session
- Built full proposal from scratch: single HTML file, 7-tab SPA
- Applied Algolia brand: Sora font, brand colors, animated grid background
- Built Overview tab: bento grid with 4 glassmorphism tiles + 3 bounce cards
- Built 3D tilt interaction on bento tiles (exact match to audit SPA)
- Built floating pill nav (matches audit SPA)
- Built right-side sticky TOC (auto-builds per tab, scroll-spy)
- Built modern timeline for Year 1 Investment tab: Q1-Y2+ with glassmorphism cards
- Built LIVE ROI CALCULATOR: all 16 team size inputs, full cascade recalculation
  - Cost savings, productivity gains, pipeline gains all scale with team size
  - Overview tile (ov-roi, ov-value) updates in real time
- Conducted salary research: 7 companies, 8 sources, March 2026
- Populated salary tables in each initiative card with verified benchmarks
- Sourced productivity multipliers: Salesforce, Bloomreach, Klue, McKinsey, P&G
- Removed all 152 em dashes from document
- Removed all emojis from UI content
- Applied proof pills to all source citations
- Fixed all font sizes: minimum 15px body, 12px uppercase labels
- Fixed layout: centered content, TOC fixed right (not displacing content)
- Built source methodology acknowledgment block (7 companies, 8 sources, with links)
- WHY NOW tile: reworded all 3 triggers for CEO audience
- Created this persistence system and /persist slash command

### Files created
- algolia-ai-director-proposal-v3.1.html — primary proposal
- arijit-new-role/STATUS.md — project status
- arijit-new-role/AGENT-PROMPT.md — parallel agent context
- arijit-new-role/CHANGELOG.md — this file
- arijit-new-role/PENDING.md — task queue
- .claude/commands/persist.md — /persist slash command

### Numbers (current state)
- ROI: 8.7× (dynamic, updates with calculator)
- Combined value: $3.94M (dynamic)
- Investment: $450K
- Direct cost savings: $959,350 (dynamic baseline)

### Decisions made
- DECIDED: 7 tabs not 8 — merged Investment + Ask
- DECIDED: "Year 1 Investment" tab label (not "Year 1 plan")
- DECIDED: "The Investment" tab label (not "The Ask")
- DECIDED: Salary never appears before ROI — CFO psychology
- DECIDED: No em dashes anywhere — "yell AI-created"
- DECIDED: No emojis in UI content — same reasoning
- DECIDED: Productivity gains are fully dynamic, not fixed
- DECIDED: Y2+ = 1 additional headcount (not 3-4)
- DECIDED: 3-5 hrs saved per prospect (not 6-8)
- DECIDED: Algolia Central removed from Year 1 timeline
- DECIDED: Funding round removed as CS trigger
- DECIDED: Legal reframed as "contract review workflow" (not transformation)

---
