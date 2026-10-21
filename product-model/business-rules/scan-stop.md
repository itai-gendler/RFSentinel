---
appliesTo:
- type: entity
  id: scan
  effect: changes
  to: Stopped
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/ScanForegroundService.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/receiver/CarAutoStart.kt
permits:
- actors:
  - user
- unattended: true
---

# The user or the car's departure stops a scan

The user stops scanning on the phone or in the car. When the car disconnects, the Product stops a scan the car started, and only that one.
