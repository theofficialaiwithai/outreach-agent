# Outreach Agent (human-in-the-loop)

A small department of AI agents that does the research and prep for personal outreach, and leaves the sending to you.

**What it does**
1. Finds targets (companies with an open role or a clear need).
2. Finds the right contact at each one.
3. Looks up and verifies their email.
4. Writes a short personal email as a Gmail **draft**.
5. Tracks everything in a Google Sheet (status, draft link, dates, follow-ups).

**What it never does:** send an email. The agent's maximum status is `Draft ready`. A human reviews, edits and sends every message.

## Quick start
1. Copy `templates/*.template.md` and fill in your own voice, offer and ideal-contact profile.
2. Create the tracking sheet using `docs/sheet-schema.md`.
3. Connect your tools (see `docs/tool-notes.md`): Gmail, Google Sheets, an email finder (Hunter or Apollo), and optionally Zapier and/or Make.
4. Follow the weekly rhythm in `docs/pipeline-and-rules.md`.

## Repo map
| Path | What it is |
|---|---|
| `docs/architecture.md` | The stages, who does what, and how the pieces connect |
| `docs/pipeline-and-rules.md` | Guardrails, weekly cadence, credit budget |
| `docs/sheet-schema.md` | Columns for the tracking sheet |
| `docs/tool-notes.md` | Lessons learned with Gmail, Sheets, Zapier, Make, Hunter, Apollo |
| `docs/roadmap.md` | Planned variants of this agent |
| `templates/` | Voice, offer, ideal-contact and email templates with placeholders |
| `make/` | A Make scenario blueprint for batch sheet writes (backup when Zapier runs out of tasks) |

## Status
Working version in daily use for a job-search/consulting outreach flow. Being verified end to end before it is packaged as a reusable template. No prospect data, contact details or personal links live in this repo.
