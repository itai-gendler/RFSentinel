---
kind: alternate
routes:
  main: Main
steps:
- text: A running SDR sweep identifies a qualifying signal.
  kind: condition
  entities:
  - entity: preferences
    effect: reads
    facts:
    - Radio
  unattended: true
  contexts:
    main:
      place: phone::radio
- text: The Product retains frequency, strength, evidence and trend for review.
  kind: product
  entities:
  - entity: radio-signal
    effect: creates
    facts:
    - Frequency
    - Strength
    - Evidence
    - Time
  - entity: radio-view
    effect: changes
    facts:
    - Spectrum
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

# Show a radio transmitting nearby

## Trigger

A running SDR sweep identifies a qualifying signal.

## Outcome

The Product retains frequency, strength, evidence and trend for review.
