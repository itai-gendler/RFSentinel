---
kind: primary
routes:
  main: Main
steps:
- text: The user dismisses the current map alert.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::map
- text: The Product hides the current alert presentation.
  kind: product
  entities:
  - entity: recent-alerts
    effect: reads
    facts: []
  actor: user
  contexts:
    main:
      place: phone::map
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/AlertCards.kt
---

# Dismiss alert

## Trigger

The user dismisses the current map alert.

## Outcome

The Product hides the current alert presentation.
