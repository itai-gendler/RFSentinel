---
kind: alternate
routes:
  main: Main
steps:
- text: The user searches for and selects an available compatible board.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::settings-external-hardware
- text: The Product saves the selected board and connects to it while scanning.
  kind: product
  entities:
  - entity: hardware
    effect: creates
    facts:
    - Kind
    - Status
    - Observations
    - Firmware
  - entity: preferences
    effect: changes
    facts:
    - External hardware
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

# Choose a Bluetooth board

## Trigger

The user searches for and selects an available compatible board.

## Outcome

The Product saves the selected board and connects to it while scanning.

## Edge cases

- No discovered compatible board produces a retry explanation.
