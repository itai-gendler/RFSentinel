---
kind: alternate
routes:
  main: Main
steps:
- text: The user chooses Un-whitelist in the car.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: car::device
- text: The Product removes the exact-address trust choice.
  kind: product
  entities:
  - entity: whitelist-entry
    effect: removes
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
  target: app/src/main/java/com/rfsentinel/app/car/DeviceDetailScreen.kt
---

# Remove trust in the car

## Trigger

The user chooses Un-whitelist in the car.

## Outcome

The Product removes the exact-address trust choice.
