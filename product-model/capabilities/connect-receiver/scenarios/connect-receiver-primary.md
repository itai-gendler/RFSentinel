---
kind: primary
routes:
  main: Main
steps:
- text: The user attaches a supported USB receiver and supplies the requested system access.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::settings-external-hardware
- text: The Product starts receiving and exposes receiver status and observations.
  kind: product
  entities:
  - entity: hardware
    effect: creates
    facts:
    - Kind
    - Status
    - Observations
    - Firmware
  actor: user
  contexts:
    main:
      place: phone::settings-external-hardware
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/usb/UsbWifi.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/esp/EspBoards.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/sdr/SdrRadio.kt
---

# Connect external receiver

## Trigger

The user attaches a supported USB receiver and supplies the requested system access.

## Outcome

The Product starts receiving and exposes receiver status and observations.

## Edge cases

- An unsupported chip or failed driver is reported in receiver status.
- A receiver requiring absent firmware remains waiting until the requested firmware is available.
- Disconnecting an adapter stops that receiver without ending other enabled receivers.
