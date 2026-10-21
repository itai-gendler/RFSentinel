---
availability:
- place: phone
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/GnssWatch.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/detect/GnssAnalyzer.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/ScanForegroundService.kt
---

# Check satellite signs

Evaluate satellite observations while GPS is operating and the category is enabled. This check does not turn on GPS itself.
