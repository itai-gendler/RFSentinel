---
appliesTo:
- type: entity
  id: nearby-device
- type: capability
  id: raise-device-alert
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/ScanForegroundService.kt
---

# Ordinary device alerts require eligible evidence and elapsed repeat time

The ordinary device alert excludes trackers and list-only matches, requires the selected confidence threshold, and waits for the per-address re-alert interval. Trusted addresses and ignored trackers do not use the ordinary matched-device alert and logging path.
