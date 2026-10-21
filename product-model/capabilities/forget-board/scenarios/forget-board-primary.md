---
kind: primary
routes:
  main: Main
steps:
- text: The user forgets the selected board.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::settings-external-hardware
- text: The Product clears the selection and ends that board connection.
  kind: product
  entities:
  - entity: preferences
    effect: changes
    facts:
    - External hardware
  - entity: hardware
    effect: changes
    facts:
    - Status
  actor: user
  contexts:
    main:
      place: phone::settings-external-hardware
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/settings/SettingsActivity.kt
---

# Forget paired board

## Trigger

The user forgets the selected board.

## Outcome

The Product clears the selection and ends that board connection.
