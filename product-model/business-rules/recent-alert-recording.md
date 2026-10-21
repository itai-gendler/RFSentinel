---
appliesTo:
- type: capability
  id: raise-device-alert
- type: capability
  id: detect-followers
- type: capability
  id: warn-camera-approach
- type: capability
  id: check-cell-signs
- type: capability
  id: check-satellite-signs
- type: capability
  id: receive-aircraft
- type: capability
  id: receive-waze-reports
- type: entity
  id: recent-alerts
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/NotificationHelper.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/data/AlertLog.kt
---

# Raised alerts are retained in recent alerts

Each raised subject replaces its previous recent-alert entry; the log holds at most forty distinct subjects, newest first. Saved positions follow GPS tagging. The transient map card may still show live position context.
