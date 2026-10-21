---
entities:
- entity: nearby-device
  shows:
  - Address
  - Name
  - Signal
  - Evidence
  - Position
- entity: known-camera
  shows:
  - Position
  - Kind
  - Label
  - Direction
  - Alerts ignored
- entity: cctv-camera
  shows:
  - Position
  - Description
  - Visibility
  - View area
- entity: trace
  shows:
  - Name
  - Times
  - Route
  - Devices
  - Counts
- entity: place
  shows:
  - Name
  - Address
  - Position
  - Saved as
- entity: route
  shows:
  - Destination
  - Stops
  - Path
  - Estimate
  - Options
  - Progress
- entity: aircraft
  shows:
  - Identification
  - Position
  - Source
  - Evidence
  - Time
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
- entity: cell-tower
  shows:
  - Identity
  - Position
- entity: recent-alerts
  shows:
  - Subject
  - Evidence
  - Time
  - Position
  - Signal
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/MapActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/MapShared.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/MapNav.kt
---

# Map

The map: the user's position, nearby devices where they were heard or pinpointed, known cameras, a recorded trace, and directions while guided.
