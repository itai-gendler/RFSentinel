---
kind: primary
routes:
  main: Main
steps:
- text: The user enters a valid address with an optional note.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::whitelist
- text: The Product saves the trust choice for that exact address.
  kind: product
  entities:
  - entity: whitelist-entry
    effect: creates
    facts:
    - Address
    - Note
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
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/ScanForegroundService.kt
---

# Whitelist device

## Trigger

The user enters a valid address with an optional note.

## Outcome

The Product saves the trust choice for that exact address.

## Edge cases

- Invalid addresses are refused by the add form.
