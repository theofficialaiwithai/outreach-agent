# Architecture

```
Target intake ──> Contact finder ──> Email lookup ──> Drafter ──> Human review/send ──> Tracker
 (job alerts,      (names, roles)    (Hunter/Apollo)  (Gmail      (you)                (Google Sheet,
  lists)                                              draft)                            follow-ups)
```

## Stages
| Stage | Input | Output | Tool |
|---|---|---|---|
| Target intake | Job alerts, company lists | Row in the sheet with company, role, status | Slack alerts, web search |
| Contact finder | Company + role | Decision-maker name (and a backup) | Web search, LinkedIn (manual), Apollo |
| Email lookup | Full name + company domain | Email + verification result | Hunter Email Finder, Apollo |
| Drafter | Row + `voice.md` + `offer.md` | Gmail draft, no send | Gmail |
| Human review | Draft | Sent email | You |
| Tracker | Everything above | Updated row | Google Sheets via Zapier or Make |

## Knowledge files (the agent's memory)
- `voice.md`: tone rules, canonical email structure, openers by status, follow-up copy.
- `offer.md`: what you offer, proof points, links. One source of truth for claims.
- `icp.md`: who to target and which titles to pitch.

Each outreach variant gets its own set of these three files. The pipeline stays the same.

## Why a sheet is the hub
Every stage reads and writes one row per target. Status values make hand-offs explicit: `Not started` -> `Draft ready` -> `Sent` (human) -> reply states (human).
