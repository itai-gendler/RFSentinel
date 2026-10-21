---
entities:
- entity: cell-tower
  shows:
  - Identity
  - Serving
  - Signal
  - Seen
  - Position
  - Warning
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/CellTowersActivity.kt
---

# Cell towers

The serving cell and its neighbours with network, identities, channel and signal, every tower seen while scanning, and the fake cell tower check status.
