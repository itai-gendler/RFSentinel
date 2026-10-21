---
kind: alternate
routes:
  main: Main
steps:
- text: The user clears the ignored-camera choices.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::settings-known-cameras
- text: The Product restores normal warning evaluation for all mapped road cameras.
  kind: product
  entities:
  - entity: known-camera
    effect: changes
    facts:
    - Alerts ignored
  actor: user
  contexts:
    main:
      place: phone::settings-known-cameras
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

# Restore warnings for all ignored cameras

## Trigger

The user clears the ignored-camera choices.

## Outcome

The Product restores normal warning evaluation for all mapped road cameras.
