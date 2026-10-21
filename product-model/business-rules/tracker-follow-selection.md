---
appliesTo:
- type: entity
  id: nearby-device
  effect: changes
  facts:
  - Following
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/ScanForegroundService.kt
permits:
- unattended: true
  when:
  - entity: preferences
    fact: Follower warnings enabled
    is: true
---

# Follower decisions require enabled follower warnings

Movement-based warnings run only while follower detection is enabled; tracker-specific pauses and ignores further determine which observations qualify.
