---
appliesTo:
- type: entity
  id: watchlist-rule
  effect: changes
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/oui/OuiWatchlist.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/SettingsBackup.kt
permits:
- actors:
  - user
---

# A new custom rule for the same condition replaces the old one

Adding a custom rule for an address, prefix, name or pattern that already has one replaces that entry, so each condition has one label and category.
