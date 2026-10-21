---
kind: alternate
routes:
  main: Main
steps:
- text: The user confirms Whitelist for the selected address.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::device
- text: The Product saves the trusted address and its description.
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
      place: phone::device
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

# Trust a selected device

## Trigger

The user confirms Whitelist for the selected address.

## Outcome

The Product saves the trusted address and its description.
