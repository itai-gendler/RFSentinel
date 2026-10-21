---
kind: alternate
routes:
  main: Main
steps:
- text: A viewed area is encountered whose camera data needs refresh with automatic downloads enabled.
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
- text: The Product refreshes available camera observations for that area.
  kind: product
  entities:
  - entity: known-camera
    effect: changes
    facts:
    - Position
    - Kind
    - Label
    - Direction
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
---

# Download cameras for the map area automatically

## Trigger

A viewed area is encountered whose camera data needs refresh with automatic downloads enabled.

## Outcome

The Product refreshes available camera observations for that area.
