---
appliesTo:
- type: entity
  id: nearby-device
  effect: removes
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/DeviceRegistry.kt
permits:
- unattended: true
---

# A device leaves the live list three minutes after it was last heard

The scan forgets a live device three minutes after it was last heard; what the app remembers about the device stays in its device history.
