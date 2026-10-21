---
kind: primary
routes:
  main: Main
steps:
- text: The user confirms clearing all logged matches.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::match-history
- text: The Product removes the match and recent-alert logs.
  kind: product
  entities:
  - entity: match-history
    effect: removes
  - entity: recent-alerts
    effect: removes
  actor: user
  contexts:
    main:
      place: phone::match-history
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/DetectionLogActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/settings/SettingsActivity.kt
---

# Clear match history

## Trigger

The user confirms clearing all logged matches.

## Outcome

The Product removes the match and recent-alert logs.
