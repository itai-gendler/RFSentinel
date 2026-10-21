---
kind: primary
routes:
  main: Main
steps:
- text: The user chooses Ignore alerts on a mapped road camera.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::map
- text: The Product keeps the selected camera’s ignored-alert choice.
  kind: product
  entities:
  - entity: known-camera
    effect: changes
    facts:
    - Alerts ignored
  actor: user
  contexts:
    main:
      place: phone::map
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/MapShared.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/alpr/IgnoredCameras.kt
---

# Ignore camera alerts

## Trigger

The user chooses Ignore alerts on a mapped road camera.

## Outcome

The Product keeps the selected camera’s ignored-alert choice.
