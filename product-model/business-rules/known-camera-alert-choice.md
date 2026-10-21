---
appliesTo:
- type: entity
  id: known-camera
  effect: changes
  facts:
  - Alerts ignored
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/MapShared.kt
permits:
- actors:
  - user
---

# The user ignores and restores warnings camera by camera

Ignore alerts silences approach warnings for one camera for good; it stays on the map, faded in the car. Resuming brings them back, for one camera or all at once.
