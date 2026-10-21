---
entities:
- entity: scan
  shows:
  - Started by car
  - Receiver status
  - Started at
- entity: nearby-device
  shows:
  - Evidence
  - Signal
  - Following
- entity: known-camera
  shows:
  - Position
  - Kind
  - Label
  - Direction
  - Alerts ignored
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/car/HomeScreen.kt
---

# Home

The car home screen: the threat headline, the next known camera on the way, recent alerts, the map, nearby devices and More, with Start or Stop and the alert sound switch.
