# /persist — Persist session state to disk

When the user says "persist" or invokes /persist, execute ALL of the following steps in order. Do not skip any step. Do not ask for confirmation — just do it.

---

## STEP 1 — Read current state first

Before writing anything, read these files to understand what's already there:
- `arijit-new-role/STATUS.md` (current snapshot)
- `arijit-new-role/CHANGELOG.md` (existing history — DO NOT modify any existing entry)
- `arijit-new-role/PENDING.md` (task queue)

This prevents overwriting work done by another parallel agent.

---

## STEP 2 — Append to CHANGELOG.md (APPEND ONLY — never modify existing lines)

Add a new entry at the TOP of CHANGELOG.md (most recent first) with this format:

```
## [DATE TIME] — Session by [identify yourself: "Primary Agent" or "Parallel Agent N"]

### What was done this session
- [bullet list of every concrete change made]

### Files modified
- algolia-ai-director-proposal-v3.1.html — [brief description]

### Numbers changed (if any)
- ROI: X → Y
- Value: $A → $B

### Decisions made (if any)
- [any new decisions, format: "DECIDED: X because Y"]
---
```

**CRITICAL:** Only add your new entry at the top. Never touch any line below your new entry's closing `---`.

---

## STEP 3 — Update STATUS.md

Overwrite STATUS.md with the current accurate state of the project. The template lives in `arijit-new-role/STATUS.md`. Update:
- The "Last updated" date at the top
- The tab status table (mark completed tabs ✅, in-progress 🔶, not started ⬜)
- The "What's Done" checklist
- The "What's Pending" checklist
- Any numbers that changed (ROI, values, etc.)
- Decisions log at the bottom (append new decisions — never remove old ones)

Do NOT change the architecture sections, file paths, CSS class reference, or JS function table unless they actually changed.

---

## STEP 4 — Update PENDING.md task queue

For each task that was completed this session, change its status from `[CLAIMED]` or `[ ]` to `[DONE yyyy-mm-dd]`.

For any new pending tasks discovered this session, add them at the bottom with status `[ ]`.

**Format for tasks:**
```
- [ ] Task description — Priority: HIGH/MED/LOW — Blocked on: [what's needed or "nothing"]
- [CLAIMED 2026-03-26 Primary] Task in progress — do not start this
- [DONE 2026-03-26] Completed task
```

---

## STEP 5 — Update AGENT-PROMPT.md if anything structural changed

Only update AGENT-PROMPT.md if any of these changed:
- File paths
- Tab structure
- Key JS function names
- Key CSS classes
- Key element IDs
- Design rules

If only content changed (text, numbers), skip this step.

---

## STEP 6 — Copy files to the proposal folder mirror

```bash
cp arijit-new-role/STATUS.md "/Users/arijitchowdhury/Library/CloudStorage/GoogleDrive-arijit.chowdhury@algolia.com/My Drive/AI/Algolia Role Proposal/arijit-new-role/STATUS.md"
cp arijit-new-role/CHANGELOG.md "/Users/arijitchowdhury/Library/CloudStorage/GoogleDrive-arijit.chowdhury@algolia.com/My Drive/AI/Algolia Role Proposal/arijit-new-role/CHANGELOG.md"
cp arijit-new-role/PENDING.md "/Users/arijitchowdhury/Library/CloudStorage/GoogleDrive-arijit.chowdhury@algolia.com/My Drive/AI/Algolia Role Proposal/arijit-new-role/PENDING.md"
cp arijit-new-role/AGENT-PROMPT.md "/Users/arijitchowdhury/Library/CloudStorage/GoogleDrive-arijit.chowdhury@algolia.com/My Drive/AI/Algolia Role Proposal/arijit-new-role/AGENT-PROMPT.md"
```

---

## STEP 7 — Git commit and push

```bash
cd "/Users/arijitchowdhury/Library/CloudStorage/GoogleDrive-arijit.chowdhury@algolia.com/My Drive/AI/Algolia Role Proposal/"
git add algolia-ai-director-proposal-v3.1.html arijit-new-role/
git commit -m "persist: [one-line summary of what changed this session]"
git push
```

---

## CONFLICT PREVENTION RULES (read before every persist)

1. **CHANGELOG.md is sacred** — you may only ADD lines at the top. If you see your session already logged, do not add a duplicate.
2. **PENDING.md task claiming** — if you are about to start working on a task, CLAIM it first by changing `[ ]` to `[CLAIMED yyyy-mm-dd AgentName]` and running persist. This signals to other agents the task is taken.
3. **Check git status first** — run `git log --oneline -3` before committing. If another agent committed in the last 5 minutes, run `git pull` first to avoid conflicts.
4. **Never delete from history** — CHANGELOG, DECISIONS, and done items in PENDING are permanent record. Do not remove them even if they seem stale.
5. **STATUS.md sections belong to no one** — any agent can update it, latest write wins. It reflects current truth, not history.
