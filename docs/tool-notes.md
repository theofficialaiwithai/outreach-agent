# Tool notes (lessons learned)

## Gmail (MCP)
- `create_draft` supports `to`, `bcc`, `subject`, `body` and `htmlBody`. Use `htmlBody` for hyperlinks.
- It cannot set the From address. Choose the send-as alias in the draft's From dropdown before sending.
- If your send-as alias is attached to the same Gmail, sending from it makes a BCC copy unnecessary.
- Once a draft is sent it leaves the Drafts folder. Check Sent before editing a draft you think still exists.
- `update_draft` merges fields: an empty field keeps the old value, so you cannot clear a BCC by passing an empty list.

## Google Sheets
- Zapier `update_row` takes `spreadsheet`, `worksheet` (ID), `row` and `COL$A`..`COL$Y` keys. Each row update costs one Zapier task.
- Dynamic enum lookups need `enum_property` and `enum_search` as top-level arguments, not inside `params`.
- Formulas written through connectors are not auto-verified. Read the sheet back to check.

## Zapier
- Task limits are per billing period. Batch rows where the multi-row action allows, and check the plan before big writes.

## Make (backup path)
- Create a Google connection first (Connections page, or from inside any Google Sheets module).
- One `google-sheets:makeAPICall` module can call `spreadsheets/{id}/values:batchUpdate` and write many ranges in a single operation. See `make/batch-write.blueprint.json`.
- Scenario scheduling: on-demand, activated, run via API.

## Hunter
- Email Finder takes a full name and a domain and is only charged when an email is found.
- Accept-all domains cannot be fully verified; flag them in the sheet.
- Set a weekly credit cap to match send volume.

## Apollo
- Check what your plan includes. Enrichment endpoints may be blocked on lower plans; fall back to Hunter or manual lookup.

## Titles vs names
- Inferred and tool-reported job titles are often wrong. Treat names as the reliable field and verify titles by hand.
