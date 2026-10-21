---
availability:
- place: phone
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/ScanForegroundService.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/alpr/KnownCameras.kt
domain: known-cameras
---

# Warn of camera approach

Raise a warning for an enabled mapped camera when successive positions show approach within its speed-dependent range.
