---
kind: alternate
routes:
  main: Main
steps:
- text: The user opens a filtered nearby list in the car.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: car::nearby
- text: The Product shows the selected observations within the car host’s list limit.
  kind: product
  entities:
  - entity: nearby-device
    effect: reads
    facts:
    - Address
    - Name
    - Vendor
    - Type
    - Sources
    - Signal
    - Evidence
    - Seen
    - Following
  actor: user
  contexts:
    main:
      place: car::nearby
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/MainActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/DeviceFilter.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/LiveWindow.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/car/DeviceListScreen.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/car/NearbyDevicesScreen.kt
---

# Browse nearby observations in the car

## Trigger

The user opens a filtered nearby list in the car.

## Outcome

The Product shows the selected observations within the car host’s list limit.
