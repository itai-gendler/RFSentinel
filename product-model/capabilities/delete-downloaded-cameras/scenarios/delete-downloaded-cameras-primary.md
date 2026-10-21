---
kind: primary
routes:
  main: Main
steps:
- text: The user confirms deletion of downloaded camera data.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::settings-known-cameras
- text: The Product removes downloaded road-camera and CCTV observations.
  kind: product
  entities:
  - entity: known-camera
    effect: removes
  - entity: cctv-camera
    effect: removes
  actor: user
  contexts:
    main:
      place: phone::settings-known-cameras
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/settings/SettingsActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/alpr/AlprStore.kt
---

# Delete downloaded cameras

## Trigger

The user confirms deletion of downloaded camera data.

## Outcome

The Product removes downloaded road-camera and CCTV observations.
