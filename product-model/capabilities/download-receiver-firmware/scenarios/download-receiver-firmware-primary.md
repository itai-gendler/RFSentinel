---
kind: primary
routes:
  main: Main
steps:
- text: The user accepts the requested firmware download for the detected adapter.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::settings-external-hardware
- text: The Product obtains the required firmware and retries receiver startup.
  kind: product
  entities:
  - entity: hardware
    effect: changes
    facts:
    - Firmware
    - Status
  actor: user
  contexts:
    main:
      place: phone::settings-external-hardware
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/usb/FirmwarePrompt.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/usb/Firmware.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/usb/UsbWifi.kt
---

# Download receiver firmware

## Trigger

The user accepts the requested firmware download for the detected adapter.

## Outcome

The Product obtains the required firmware and retries receiver startup.

## Edge cases

- A failed or invalid download keeps the receiver waiting and reports failure.
