# Tracking sheet schema (one row per target)

| Col | Header | Notes |
|---|---|---|
| A | Company | |
| B | Send wave | 1-5 |
| C | Your status | e.g. Open application / No application / Rejected |
| D | Role | The open role used as the hook |
| E | Role fit (1-5) | Optional scoring |
| F | Timing (1-5) | Optional scoring |
| G | Score reason + source | |
| H | Primary title (inferred) | Treat as a guess, not a fact |
| I | Contact name (primary) | Names are the reliable field |
| J | Backup title | |
| K | Contact name (backup) | |
| L | Contact email | |
| M | Email source | e.g. Hunter, Apollo, supplied |
| N | Email verified? | valid / accept-all / unknown |
| O | Offer to lead with | Build, Teach or both |
| P | Opening line | Per `voice.md` |
| Q | Brief link | Optional research brief |
| R | Draft status | Not started / Draft ready / Sent / On hold |
| S | Gmail draft link | |
| T | Date sent | Human-entered. Drives follow-up dates. |
| U | Follow-up 1 due | `=IF(T2="","",T2+5)` |
| V | Follow-up 2 due | `=IF(T2="","",T2+12)` |
| W | Reply status | Human-entered |
| X | Next action | Who does what next |
| Y | Notes | |
