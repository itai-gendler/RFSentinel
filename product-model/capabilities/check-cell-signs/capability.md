---
availability:
- place: phone
references:
- kind: spec
  role: intent
  target: docs/SIGNATURES.md
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/CellMonitor.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/detect/CellAnalyzer.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/ScanForegroundService.kt
---

# Check cell signs

Evaluate the cell information Android exposes for heuristic warning signs while the category is enabled.
