---
kind: primary
routes:
  main: Main
steps:
- text: The user inspects the current map alert.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::map
- text: The Product presents its subject, evidence, confidence and available location context.
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
      place: phone::map
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/AlertCards.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/NotificationHelper.kt
---

# Review alerts

## Trigger

The user inspects the current map alert.

## Outcome

The Product presents its subject, evidence, confidence and available location context.
