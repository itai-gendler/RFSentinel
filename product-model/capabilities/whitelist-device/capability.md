---
availability:
- place: phone
- place: car
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/whitelist/WhitelistActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/DeviceActions.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/ScanForegroundService.kt
domain: whitelist
---

# Whitelist device

Trust an exact address so its ordinary matching path no longer logs or raises device alerts. It can still appear in remembered devices and traces.
