---
kind: primary
routes:
  main: Main
steps:
- text: The user reviews external hardware status.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::settings-external-hardware
- text: The Product shows attached or selected receivers and any waiting or failure state.
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
      place: phone::settings-external-hardware
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/settings/SettingsActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/usb/UsbWifi.kt
---

# Browse external receivers

## Trigger

The user reviews external hardware status.

## Outcome

The Product shows attached or selected receivers and any waiting or failure state.
