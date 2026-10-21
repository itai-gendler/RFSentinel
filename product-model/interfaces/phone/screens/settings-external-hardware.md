---
entities:
- entity: preferences
  shows:
  - External hardware
  - Frame collection enabled
  collects:
  - External hardware
  - Frame collection enabled
- entity: hardware
  shows:
  - Kind
  - Status
  - Observations
  - Firmware
- entity: frame-recording
  shows:
  - Frames
  - File
  - Stop reason
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/settings/SettingsActivity.kt
---

# External hardware

The External hardware section of Settings: boards, USB WiFi adapters, frame recording and requested networks.
