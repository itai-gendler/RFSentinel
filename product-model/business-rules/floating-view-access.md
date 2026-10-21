---
appliesTo:
- type: entity
  id: nearby-device
  effect: reads
  contexts:
  - place: phone::floating-views
- type: entity
  id: known-camera
  effect: reads
  contexts:
  - place: phone::floating-views
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/ThreatBubble.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/FloatingMap.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/ScanForegroundService.kt
permits:
- actors:
  - user
  when:
  - entity: android-access
    fact: Overlay permission
    is: Granted
  - entity: scan
    fact: Active
    is: true
  - entity: preferences
    fact: Floating views
    is: At least one view enabled
---

# Floating views require a running scan and overlay access

Floating subjects can be displayed during an active scan when Android allows overlays and a floating view is selected.
