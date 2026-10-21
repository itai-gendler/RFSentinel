---
entities:
- entity: preferences
  shows:
  - Known cameras
  collects:
  - Known cameras
- entity: known-camera
  shows:
  - Position
  - Kind
  - Label
  - Direction
  - Alerts ignored
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/settings/SettingsActivity.kt
---

# Known cameras

The Known cameras section of Settings: downloads, radius, warnings and CCTV cameras.
