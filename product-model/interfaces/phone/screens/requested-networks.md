---
entities:
- entity: requested-network
  shows:
  - Name
  - Devices
  - Seen
  - Signal
- entity: watchlist-rule
  shows:
  - Match
  - Label
  - Source
  - Score
  - Category
  - Custom
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/probes/ProbeListActivity.kt
---

# Requested networks

The WiFi network names nearby devices asked for, with the devices that asked for each, collected through a USB WiFi adapter or Marauder board.
