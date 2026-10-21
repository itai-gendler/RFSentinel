---
entities:
- entity: preferences
  shows:
  - Detection
  - Aircraft enabled
  - Waze ready
  - Online aircraft enabled
  - Cell checks enabled
  - Satellite checks enabled
  collects:
  - Detection
  - Aircraft enabled
  - Waze ready
  - Online aircraft enabled
  - Cell checks enabled
  - Satellite checks enabled
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/settings/SettingsActivity.kt
---

# What to detect

The What to detect section of Settings: equipment categories, watchlist presets and the optional online sources.
