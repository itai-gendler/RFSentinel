---
appliesTo:
- type: entity
  id: nearby-device
  effect: changes
  facts:
  - Address
  - Name
  - Vendor
  - Type
  - Sources
  - Signal
  - Evidence
  - Seen
  - Decoded data
  - Position
  - Linked address
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/DeviceRegistry.kt
permits:
- unattended: true
---

# Receivers can refresh live observation evidence

The receiver lifecycle updates observation data and range state independently of user-initiated Locate and movement warnings.
