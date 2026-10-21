---
appliesTo:
- type: entity
  id: requested-network
  effect: creates
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/ScanForegroundService.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/data/ProbeLog.kt
permits:
- unattended: true
  when:
  - entity: preferences
    fact: Frame collection enabled
    is: true
---

# Requested names are kept only for selected collection or a trace

The collector retains requested names when optional collection is enabled or trace recording requires them.
