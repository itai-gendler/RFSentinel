---
appliesTo:
- type: entity
  id: known-camera
  effect: changes
  facts:
  - Position
  - Kind
  - Label
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/alpr/AlprStore.kt
permits:
- unattended: true
---

# Downloads refresh mapped camera details

Downloading an area again replaces each camera's mapped position, kind and label with the current map data.
