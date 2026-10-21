---
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/data/TrackerMutes.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/DeviceActions.kt
---

# Ignored tracker

A tracker suppression choice that can expire or follow a likely address rotation.

## Information kept

- **Address** — Address currently covered.
- **Kind** — Observed tracker match label.
- **Mode** — Today only or mine with best-effort address continuation.
- **Until** — Time the temporary ignore expires.
- **Last heard** — Most recent time and signal used to continue an ignore.
