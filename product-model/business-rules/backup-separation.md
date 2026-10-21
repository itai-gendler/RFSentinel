---
appliesTo:
- type: entity
  id: preferences
- type: entity
  id: custom-theme
- type: entity
  id: watchlist-rule
- type: entity
  id: place
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/SettingsBackup.kt
---

# Settings backups omit secrets and transient state

Backups retain the supported durable choices and selected assets, excluding API secrets, service acknowledgments, folder grants and transient snoozes. Restoring selected sections replaces their backed-up values; a malformed backup is rejected before application.
