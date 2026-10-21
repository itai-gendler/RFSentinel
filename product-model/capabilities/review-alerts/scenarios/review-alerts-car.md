---
kind: alternate
routes:
  main: Main
steps:
- text: The user opens Recent alerts.
  kind: actor
  entities:
  - entity: recent-alerts
    effect: reads
    facts: []
  actor: user
  contexts:
    main:
      place: car::alerts
- text: The Product shows the most recent distinct alerts and provides available subject destinations.
  kind: product
  entities:
  - entity: recent-alerts
    effect: reads
    facts:
    - Subject
    - Evidence
    - Time
    - Position
    - Signal
  actor: user
  contexts:
    main:
      place: car::alerts
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/AlertCards.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/NotificationHelper.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/car/RecentAlertsScreen.kt
---

# Review recent alerts in Android Auto

## Trigger

The user opens Recent alerts.

## Outcome

The Product shows the most recent distinct alerts and provides available subject destinations.

## Edge cases

- An older alert uses its recorded location when the current online subject is no longer available.
