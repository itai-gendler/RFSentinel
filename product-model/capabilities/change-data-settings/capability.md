---
availability:
- place: phone
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/settings/SettingsActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/Prefs.kt
domain: data
---

# Change data settings

Change the Data section of Settings: how many days history is kept (90 by default, 0 keeps it forever) and live export, which rewrites match and map files every 30 seconds in a folder the user chooses.
