---
kind: primary
routes:
  main: Main
steps:
- text: The user chooses Alert again for a mapped camera.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::map
- text: The Product clears that ignored-alert choice.
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
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/settings/SettingsActivity.kt
---

# Resume camera alerts

## Trigger

The user chooses Alert again for a mapped camera.

## Outcome

The Product clears that ignored-alert choice.
