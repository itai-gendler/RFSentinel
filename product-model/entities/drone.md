---
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/detect/RemoteId.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/DeviceDetailActivity.kt
---

# Drone report

Remote ID information assembled from a drone broadcast.

## Information kept

- **Identification** — Reported serial or identifier and descriptive fields.
- **Position** — Reported aircraft coordinates, altitude, speed and heading.
- **Operator position** — Reported operator or take-off location.
- **Last heard** — Time and radio source of the latest report.
