---
availability:
- place: phone
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/online/WazeWatch.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/online/WazePolice.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/ScanForegroundService.kt
domain: waze-status
---

# Receive Waze reports

Refresh and re-score optional crowd reports. Source choice changes the request path; movement re-evaluates already fetched reports between requests.
