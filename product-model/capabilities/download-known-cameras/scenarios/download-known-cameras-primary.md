---
kind: primary
routes:
  main: Main
steps:
- text: The user starts a download around their location.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::settings-known-cameras
- text: The Product saves available mapped cameras and reports completed and failed areas.
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

# Download cameras around the user

## Trigger

The user starts a download around their location.

## Outcome

The Product saves available mapped cameras and reports completed and failed areas.

## Edge cases

- Without a usable location, the radius download reports that no location is available.
- A failed area can leave partial coverage; completion reports missing areas instead of claiming full coverage.
- The bulk US and Canada collection uses regional map snapshots and can refresh weekly on WiFi.
