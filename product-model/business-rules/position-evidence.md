---
appliesTo:
- type: entity
  id: nearby-device
- type: entity
  id: cell-tower
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/DeviceRegistry.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/ScanForegroundService.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/CellTowerStore.kt
---

# Observation positions preserve their source and uncertainty

A reported vehicle position takes precedence over a fitted estimate, which takes precedence over where the phone heard the strongest signal. Placement uses recent sufficiently accurate location fixes. Fitted positions and rough signal distances are estimates; a cell-tower map point is a strongest-observation location.
