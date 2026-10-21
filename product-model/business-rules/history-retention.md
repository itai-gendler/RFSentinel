---
appliesTo:
- type: entity
  id: remembered-device
- type: entity
  id: match-history
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/ScanForegroundService.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/data/KnownDeviceEntity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/settings/SettingsActivity.kt
---

# Automatic retention preserves favorites and annotations

At the start of a scan, a positive retention period prunes old match entries and old remembered addresses without a favorite, own name or note. Zero disables age-based pruning. Explicitly forgetting history retains favorites only.
