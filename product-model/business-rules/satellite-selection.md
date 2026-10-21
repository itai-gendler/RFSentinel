---
appliesTo:
- type: entity
  id: satellite-status
  effect: changes
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/ScanForegroundService.kt
permits:
- unattended: true
  when:
  - entity: preferences
    fact: Satellite checks enabled
    is: true
---

# GPS and satellite checks run only while their category is on

The GPS and satellite checks look at the satellites the phone hears only while their category is on and the phone's GPS is already running; they never turn the GPS on.
