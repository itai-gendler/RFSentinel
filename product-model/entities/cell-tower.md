---
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/CellMonitor.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/CellTowerStore.kt
---

# Cell tower

Serving or neighboring cell information supplied by the phone modem.

## Information kept

- **Identity** — Radio generation, network, cell identity and area.
- **Serving** — Whether the modem currently uses this cell.
- **Signal** — Reported strength and channel.
- **Seen** — First and latest sighting.
- **Position** — Where the phone heard this cell strongest, when known.
- **Warning** — Heuristic anomaly and its evidence.
