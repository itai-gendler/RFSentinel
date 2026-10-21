---
kind: alternate
routes:
  main: Main
steps:
- text: An enabled CCTV download covers the requested surrounding area.
  kind: condition
  entities:
  - entity: preferences
    effect: reads
    facts:
    - Known cameras
  unattended: true
  contexts:
    main:
      place: phone::map
- text: The Product retains mapped surveillance-camera positions and view information.
  kind: product
  entities:
  - entity: cctv-camera
    effect: creates
    facts:
    - Position
    - Description
    - Visibility
    - View area
  contexts:
    main:
      place: phone::map
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
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/alpr/Cctv.kt
---

# Download CCTV cameras around the user

## Trigger

An enabled CCTV download covers the requested surrounding area.

## Outcome

The Product retains mapped surveillance-camera positions and view information.
