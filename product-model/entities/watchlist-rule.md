---
domain: watchlist
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/oui/OuiEntry.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ouilist/OuiListActivity.kt
---

# Watchlist rule

A named condition that contributes a match when received evidence satisfies it.

## Information kept

- **Match** — Exact address, prefix, name, vendor, requested network or observed fingerprint.
- **Label** — User-facing description of the match.
- **Source** — Preset reference or user-supplied provenance.
- **Score** — Confidence contribution.
- **Category** — Equipment category.
- **Custom** — Whether the user added this entry.
