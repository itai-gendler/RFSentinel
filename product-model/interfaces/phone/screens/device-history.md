---
entities:
- entity: remembered-device
  shows:
  - Address
  - Name
  - Vendor
  - Type
  - First seen
  - Last seen
  - Sessions
  - Sightings
  - Favorite
  - Own name
  - Note
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/DeviceHistoryActivity.kt
---

# Device history

Every device the app remembers, in range or not, searchable by address, name, vendor, type, the user's own name or note, and filtered to favorites, flagged before or seen today.
