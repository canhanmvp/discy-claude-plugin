---
name: brain-weekly-review
description: Run a weekly review over the user's Discy workspace — tasks, goals, projects, notes — and produce Outcome / Output / Actions / Lessons / One Thing Tomorrow. Use when the user says "weekly review", "review my week", or "what did I get done".
---

Use the Discy MCP tools (`search`, `fetch`). Read-only; never change items.

1. Search for active items with a few short queries (e.g. the user's project
   names, "week", current goal titles). Results are bounded; state that coverage
   may be incomplete.
2. If the user wants their reflections included, call `request_optional_access` with `data: "reflections"`
   (the user must approve it once), then `search` for recent "Reflection" entries and `fetch` the last few. They
   are private: summarise themes only when asked, quote sparingly, never repeat them elsewhere.
   Fetch the relevant task, goal and project items (cap about 8). Report only
   returned fields: status, progress, dates. Never invent deadlines or completion.
3. Output, in this order:
   - **Outcome** — what moved, by goal/project
   - **Output** — concrete deliverables found
   - **Actions** — planned vs done, and what slipped
   - **Lessons** — 2–3 grounded observations
   - **One thing tomorrow** — a single suggestion for the user to confirm
4. Keep calculations deterministic: count and compare returned statuses; do not
   estimate hidden items.
5. Suggestions are not saved anywhere. Offer to draft a note via the
   `brain-capture` skill.
