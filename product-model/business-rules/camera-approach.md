---
appliesTo:
- type: entity
  id: known-camera
- type: entity
  id: cctv-camera
references:
- kind: spec
  role: intent
  target: docs/SIGNATURES.md
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/ScanForegroundService.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/alpr/KnownCameras.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/alpr/Cctv.kt
---

# Mapped-camera warnings require observed approach

A camera warns once a second location fix shows the user at least 3 m closer and within its range: for a plate reader at least 150 m, or about 20 seconds of travel up to 600 m; for a speed or red-light camera about 30 seconds, 300 to 900 m. While moving, a camera facing 55° or more across the user's way watches another road and stays quiet. Each camera warns at most every 30 minutes, ignored cameras never warn, and CCTV cameras are shown on the map only.
