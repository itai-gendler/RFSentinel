---
availability:
- place: phone
- place: car
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/ScanForegroundService.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/NotificationHelper.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/AlertPlayer.kt
---

# Raise device alert

Raise an ordinary match alert when its confidence, suppression choices and re-alert interval allow it. Tracker following and drone-overhead warnings have their own triggers.
