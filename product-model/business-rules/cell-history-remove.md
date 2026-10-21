---
appliesTo:
- type: entity
  id: cell-tower
  effect: removes
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/settings/SettingsActivity.kt
permits:
- actors:
  - user
---

# Only the user forgets remembered cell towers

Forget device history clears the cell towers remembered for the fake cell tower checks, so their new or returning status starts over; remembered devices that are not favorites go with it.
