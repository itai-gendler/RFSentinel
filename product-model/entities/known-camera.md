---
domain: known-cameras
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/alpr/KnownCameras.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/MapShared.kt
---

# Known camera

A downloaded plate-reader, speed or red-light camera observation from map data.

## Information kept

- **Position** — Mapped location and map reference.
- **Kind** — Plate reader, speed camera or red-light camera.
- **Label** — Mapped maker, operator or camera description.
- **Direction** — Mapped facing or the user’s local direction when no mapped direction is available.
- **Alerts ignored** — Whether approach warnings are silenced for this camera.
