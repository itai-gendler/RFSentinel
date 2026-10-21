---
appliesTo:
- type: entity
  id: known-camera
  effect: changes
  facts:
  - Direction
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/MapShared.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/alpr/CameraDirections.kt
permits:
- actors:
  - user
  when:
  - fact: Direction
    is: No mapped direction
- unattended: true
---

# The user supplies a camera direction only when map data has none

The local direction choice fills a missing mapped direction and can be cleared again. Download refreshes may supply mapped direction information.
