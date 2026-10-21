---
kind: alternate
routes:
  main: Main
steps:
- text: The user chooses the bulk US and Canada camera download.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::settings-known-cameras
- text: The Product retains the downloaded plate-camera collection and reports its result.
  kind: product
  entities:
  - entity: known-camera
    effect: creates
    facts:
    - Position
    - Kind
    - Label
    - Direction
    - Alerts ignored
  actor: user
  contexts:
    main:
      place: phone::settings-known-cameras
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/alpr/AlprStore.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/alpr/CameraPrefetch.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/alpr/DeflockBulk.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/settings/SettingsActivity.kt
---

# Download the regional plate-camera collection

## Trigger

The user chooses the bulk US and Canada camera download.

## Outcome

The Product retains the downloaded plate-camera collection and reports its result.
