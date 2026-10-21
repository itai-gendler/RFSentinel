---
kind: primary
routes:
  main: Main
steps:
- text: The user opens the radio view.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::radio
- text: The Product shows the available sweep or tuned spectrum and receiver status.
  kind: product
  entities:
  - entity: radio-view
    effect: reads
    facts:
    - Mode
    - Frequency
    - Spectrum
  - entity: radio-signal
    effect: reads
    facts:
    - Frequency
    - Strength
    - Evidence
    - Time
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
      place: phone::radio
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/WaterfallActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/sdr/RadioLog.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/sdr/SdrWaterfall.kt
---

# Browse radio waterfall

## Trigger

The user opens the radio view.

## Outcome

The Product shows the available sweep or tuned spectrum and receiver status.

## Edge cases

- The receiver observes RF energy and supported metadata; the radio sweep does not decode voice conversations.
