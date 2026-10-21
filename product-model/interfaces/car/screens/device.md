---
entities:
- entity: nearby-device
  shows:
  - Address
  - Name
  - Vendor
  - Type
  - Sources
  - Signal
  - Evidence
  - Seen
  - Following
- entity: recent-alerts
  shows:
  - Subject
  - Evidence
  - Time
  - Position
  - Signal
- entity: drone
  shows:
  - Identification
  - Position
- entity: watchlist-rule
  shows:
  - Match
  - Label
- entity: whitelist-entry
  shows:
  - Address
- entity: tracker-ignore
  shows:
  - Address
  - Mode
- entity: remembered-device
  shows:
  - Favorite
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/car/DeviceDetailScreen.kt
---

# Device details

One device on the car screen: what it is, how sure, about how far, and Whitelist, Watch, Favorite and the tracker ignore choices.
