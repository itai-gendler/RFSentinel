---
kind: alternate
routes:
  main: Main
steps:
- text: The user chooses Un-whitelist.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::device
- text: The Product removes the exact-address trust choice.
  kind: product
  entities:
  - entity: whitelist-entry
    effect: removes
  actor: user
  contexts:
    main:
      place: phone::device
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/whitelist/WhitelistActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/DeviceActions.kt
---

# Remove trust in device details

## Trigger

The user chooses Un-whitelist.

## Outcome

The Product removes the exact-address trust choice.
