---
appliesTo:
- type: entity
  id: known-camera
  effect: removes
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/settings/SettingsActivity.kt
permits:
- actors:
  - user
---

# The user deletes downloaded cameras

Delete downloaded cameras removes every saved plate, speed, red-light and CCTV camera; they download again as the map is used.
