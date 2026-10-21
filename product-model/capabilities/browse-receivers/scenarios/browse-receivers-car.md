---
kind: alternate
routes:
  main: Main
steps:
- text: The user opens Hardware in Android Auto.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: car::hardware
- text: The Product shows the current external receiver statuses.
  kind: product
  entities:
  - entity: hardware
    effect: reads
    facts:
    - Kind
    - Status
    - Observations
    - Firmware
  actor: user
  contexts:
    main:
      place: car::hardware
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/settings/SettingsActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/usb/UsbWifi.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/car/HardwareScreen.kt
---

# Review receiver status in the car

## Trigger

The user opens Hardware in Android Auto.

## Outcome

The Product shows the current external receiver statuses.
