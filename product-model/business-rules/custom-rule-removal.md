---
appliesTo:
- type: entity
  id: watchlist-rule
  effect: removes
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ouilist/OuiAdapter.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/oui/OuiWatchlist.kt
permits:
- actors:
  - user
  when:
  - fact: Custom
    is: true
---

# Only custom watchlist rules can be removed

The remove controls act on user-added entries. Bundled conditions are selected through presets.
