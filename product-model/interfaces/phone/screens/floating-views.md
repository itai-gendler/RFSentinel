---
entities:
- entity: nearby-device
  shows:
  - Evidence
  - Following
  - Position
- entity: known-camera
  shows:
  - Position
  - Kind
  - Alerts ignored
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/ThreatBubble.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/FloatingMap.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/ScanForegroundService.kt
---

# Floating views

Current threat summary and optional surroundings map over other applications.
