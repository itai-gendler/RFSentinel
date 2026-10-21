---
appliesTo:
- type: entity
  id: frame-recording
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/usb/PcapRecorder.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/settings/SettingsActivity.kt
---

# Only the newest frame recording is kept

Starting a frame recording replaces the previous one, and a recording never grows past 200 MB.
