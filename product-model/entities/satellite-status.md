---
singleton: true
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/GnssWatch.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/GnssActivity.kt
---

# GPS and satellites

The phone receiver’s current satellite observations and heuristic warning signs.

## Information kept

- **Satellites** — Constellations, satellite counts and used-in-fix information.
- **Signal** — Signal levels and changes across the observed sky.
- **Warning** — Current heuristic warning and supporting evidence.
