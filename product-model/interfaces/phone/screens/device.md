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
  - Decoded data
  - Position
  - Following
  - Linked address
  - Locate active
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
  collects:
  - Own name
  - Note
- entity: drone
  shows:
  - Identification
  - Position
  - Operator position
  - Last heard
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
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/DeviceDetailActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/DeviceActions.kt
---

# Device details

Evidence, observed identity clues, raw broadcasts, signal history and saved annotations for one selected address.
