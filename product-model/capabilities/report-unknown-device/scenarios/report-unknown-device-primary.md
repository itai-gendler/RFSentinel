---
kind: primary
routes:
  main: Main
steps:
- text: The user opens Report unknown device and reviews the proposed content.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::device
- text: The Product supplies the signature report through copy or the Android share chooser.
  kind: product
  entities:
  - entity: nearby-device
    effect: reads
    facts:
    - Vendor
    - Type
    - Decoded data
  actor: user
  contexts:
    main:
      place: phone::device
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/DeviceActions.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/detect/SignatureReport.kt
---

# Report unknown device

## Trigger

The user opens Report unknown device and reviews the proposed content.

## Outcome

The Product supplies the signature report through copy or the Android share chooser.

## Edge cases

- No current advertisement means there is no signature report to prepare.
- The report omits the full address, serials, location and times.
