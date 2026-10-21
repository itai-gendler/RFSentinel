---
kind: primary
routes:
  main: Main
steps:
- text: The user removes a trusted address.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::whitelist
- text: The Product removes that trust choice and offers Undo on the phone list.
  kind: product
  entities:
  - entity: whitelist-entry
    effect: removes
  actor: user
  contexts:
    main:
      place: phone::whitelist
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/whitelist/WhitelistActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/DeviceActions.kt
---

# Remove whitelist entry

## Trigger

The user removes a trusted address.

## Outcome

The Product removes that trust choice and offers Undo on the phone list.
