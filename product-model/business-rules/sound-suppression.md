---
appliesTo:
- type: entity
  id: preferences
  facts:
  - Alert mute
  - Snoozed until
  - Alerts
  - Navigation
  - General
- type: entity
  id: recent-alerts
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/AlertPlayer.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/AlertCards.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/NotificationHelper.kt
---

# Mute and snooze silence alert sound and speech

Mute and snooze silence alert sound and speech. Vibration follows its own switch, current visual alerts can remain visible, and spoken navigation follows its separate guidance choice. Discreet mode reduces disclosed notification and alert-card detail.
