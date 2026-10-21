---
availability:
- place: phone
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/settings/SettingsActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/usb/PcapRecorder.kt
domain: external-hardware
---

# Record frames

Start a raw capture of received USB WiFi or V2X frames during a scan. Only the newest recording is retained.
