---
appliesTo:
- type: entity
  id: watchlist-rule
  effect: creates
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/oui/OuiWatchlist.kt
permits:
- actors:
  - user
---

# The user adds custom watchlist rules

Custom rules are the user's own, added from the watchlist, a device's details (Watch and I saw it), a requested network or an imported file. Preset entries come only with their preset.
