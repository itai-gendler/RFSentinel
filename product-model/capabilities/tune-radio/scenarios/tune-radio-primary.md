---
kind: primary
routes:
  main: Main
steps:
- text: The user chooses a valid tuning frequency.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::radio
- text: The Product holds the selected frequency and updates the tuned spectrum view.
  kind: product
  entities:
  - entity: radio-view
    effect: changes
    facts:
    - Mode
    - Frequency
    - Spectrum
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
  target: app/src/main/java/com/rfsentinel/app/sdr/SdrRadio.kt
---

# Tune radio

## Trigger

The user chooses a valid tuning frequency.

## Outcome

The Product holds the selected frequency and updates the tuned spectrum view.

## Edge cases

- An out-of-range or invalid frequency is reported.
- Without a running SDR the application explains that it cannot tune.
