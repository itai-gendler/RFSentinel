---
appliesTo:
- type: entity
  id: waze-report
  effect: creates
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/online/WazeWatch.kt
permits:
- unattended: true
  when:
  - entity: preferences
    fact: Waze ready
    is: true
---

# Waze reports need a source the user set up

Waze reports are fetched only while the Waze category is on and a source is ready: the user's own OpenWeb Ninja key, or Waze direct once the user accepts what it sends.
