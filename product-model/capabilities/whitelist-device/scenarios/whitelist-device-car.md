---
kind: alternate
routes:
  main: Main
steps:
- text: The user chooses Whitelist or the applicable Ignore alert action.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: car::device
- text: The Product saves the trusted exact address.
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
      place: car::device
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
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/car/DeviceDetailScreen.kt
---

# Trust an address from the car

## Trigger

The user chooses Whitelist or the applicable Ignore alert action.

## Outcome

The Product saves the trusted exact address.
