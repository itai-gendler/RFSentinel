---
availability:
- place: phone
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/ScanForegroundService.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/DeviceRegistry.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/PlaceFollow.kt
---

# Detect followers

Use observed continuity and movement to flag equipment that may be following. The configured time and displacement must both be met.
