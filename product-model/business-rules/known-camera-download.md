---
appliesTo:
- type: entity
  id: known-camera
  effect: creates
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/alpr/AlprStore.kt
permits:
- actors:
  - user
- unattended: true
---

# Cameras are downloaded by the user or automatically

Known cameras come from OpenStreetMap and DeFlock: around the user within the download radius, every mapped plate reader in the US and Canada at once, or the map area in view while Download automatically is on.
