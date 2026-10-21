---
kind: alternate
routes:
  main: Main
steps:
- text: The user opens a device in the car.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: car::device
- text: The Product shows current signal and evidence, or the last recorded alert when the live observation has
    gone.
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
  - entity: recent-alerts
    effect: reads
    facts:
    - Subject
    - Evidence
    - Time
    - Position
    - Signal
  actor: user
  contexts:
    main:
      place: car::device
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/DeviceDetailActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/car/DeviceDetailScreen.kt
---

# Read concise device evidence in the car

## Trigger

The user opens a device in the car.

## Outcome

The Product shows current signal and evidence, or the last recorded alert when the live observation has gone.

## Edge cases

- If neither current data nor a previous alert exists, the car reports that the device is out of range.
