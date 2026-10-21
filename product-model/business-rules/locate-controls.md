---
appliesTo:
- type: entity
  id: nearby-device
  effect: changes
  facts:
  - Locate active
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/DeviceDetailActivity.kt
permits:
- actors:
  - user
---

# The user starts and stops Locate

Locate beeps faster as the selected device's signal gets stronger, carries on when the device's address is linked to a new one, and runs until the user stops it.
