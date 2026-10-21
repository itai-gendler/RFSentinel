---
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/data/AlertLog.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/car/RecentAlertsScreen.kt
---

# Recent alerts

A local review log of the latest distinct alerts, available in Android Auto.

## Information kept

- **Subject** — Device or place that raised the alert.
- **Evidence** — Label, category, confidence, reason and following indication.
- **Time** — Most recent alert time for the subject.
- **Position** — Optional saved location.
- **Signal** — Signal when the alert concerned a radio device.
