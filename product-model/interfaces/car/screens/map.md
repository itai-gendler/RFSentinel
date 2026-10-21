---
entities:
- entity: nearby-device
  shows:
  - Position
  - Evidence
- entity: known-camera
  shows:
  - Position
  - Kind
  - Alerts ignored
- entity: drone
  shows:
  - Position
- entity: route
  shows:
  - Destination
  - Stops
  - Path
  - Estimate
  - Options
  - Progress
- entity: place
  shows:
  - Name
  - Address
  - Position
  - Saved as
- entity: cell-tower
  shows:
  - Position
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/car/LiveMapScreen.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/car/CarMapRenderer.kt
---

# Live map & navigation

RF Sentinel's own map on the car screen: devices, known cameras, drones and the car's position, with directions while guided.
