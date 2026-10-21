---
domain: waze-status
singleton: true
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/online/WazeWatch.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/WazeStatusActivity.kt
---

# Waze status

The current state of the optional online report checks.

## Information kept

- **State** — Active or paused checks, next due time and current provider.
- **Checks** — Last request time, duration, results and recent checks.
- **Status** — Waiting condition, update result or error.
