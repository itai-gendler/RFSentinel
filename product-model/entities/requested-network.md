---
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/data/ProbeLog.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/probes/ProbeListActivity.kt
---

# Requested network

A network name observed in nearby WiFi probe requests.

## Information kept

- **Name** — Requested WiFi network name.
- **Devices** — Addresses heard requesting that name.
- **Seen** — First and most recent request.
- **Signal** — Strongest observed request signal.
