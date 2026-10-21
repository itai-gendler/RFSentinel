---
entities:
- entity: recent-alerts
  shows:
  - Subject
  - Evidence
  - Time
  - Position
  - Signal
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/car/RecentAlertsScreen.kt
---

# Recent alerts

The last 40 alerts in the car, devices, cameras and cell warnings, kept after the device is gone.
