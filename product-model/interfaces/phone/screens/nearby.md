---
entities:
- entity: scan
  shows:
  - Started by car
  - Receiver status
  - Started at
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
- entity: preferences
  shows:
  - Alert mute
  - Snoozed until
- entity: cell-tower
  shows:
  - Identity
  - Serving
  - Signal
- entity: waze-report
  shows:
  - Type
  - Position
  - Age
  - Confirmations
  - Relevance
  - Confidence
  - Level
  - Source
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/MainActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/LiveWindow.kt
---

# Nearby devices

The main screen: the threat banner, the live list and radar of everything in range with its badges, filter chips with live counts, and the scan status.
