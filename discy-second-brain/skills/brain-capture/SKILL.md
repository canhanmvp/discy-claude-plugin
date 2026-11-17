---
name: brain-capture
description: After finishing work or learning something, distil it into a source-backed note draft the user can save into Discy. Use when the user says "save this", "capture", "write this up as a note", or at the end of a session with decisions or lessons worth keeping.
---

The Discy MCP is currently read-only: there is no tool that creates or edits notes.
Do not claim anything was saved.

1. Ask nothing unless the topic is unclear; draft from the conversation.
2. Produce one note draft in Markdown:
   - Title (specific, searchable)
   - Source: where it came from (URL, repo path, PR, date) — never invent one
   - Status: `raw` | `processed` | `applied`
   - Key points (3–7 bullets), Decisions, Open questions
   - Links: related Discy items found via `search` (use `[[Title]]` wiki-links)
3. Before drafting, optionally run `search` on the title to avoid duplicating an
   existing note; if one exists, propose an "append" section instead.
4. Suggest a destination folder: reuse the `folder` path of related notes found in
   step 3 (the most common one), or say no folder fits. Never claim the folder
   exists unless a search result showed it; the MCP cannot create folders.
5. Present the draft in a single fenced block, then tell the user how to save it:
   paste into a new Discy note (in the suggested folder), or use the Discy Web
   Clipper quick-save.
6. Keep personal data minimal; omit secrets, tokens and credentials entirely.
