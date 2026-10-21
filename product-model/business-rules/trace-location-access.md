---
appliesTo:
- type: entity
  id: trace
  effect: creates
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/MapActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/ScanForegroundService.kt
permits:
- actors:
  - user
  when:
  - entity: android-access
    fact: Location permission
    is: Granted
- unattended: true
  when:
  - entity: android-access
    fact: Location permission
    is: Granted
  - entity: preferences
    fact: Location
    is: Automatic trace recording enabled
---

# Trace recording starts with location access

Starting a route recording requires precise location access. Automatic trace recording also requires its setting to be enabled.
