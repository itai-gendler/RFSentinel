---
appliesTo:
- type: entity
  id: nearby-device
  effect: creates
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/ScanForegroundService.kt
permits:
- unattended: true
---

# Devices enter the live list only from a running scan

A device is listed only after an enabled radio of the phone or a connected receiver hears it while scanning.
