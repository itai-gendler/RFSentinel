---
kind: primary
routes:
  main: Main
steps:
- text: The user chooses Back to sweep.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::radio
- text: The Product clears the held frequency and resumes the sweep.
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

# Resume radio sweep

## Trigger

The user chooses Back to sweep.

## Outcome

The Product clears the held frequency and resumes the sweep.

## Edge cases

- Leaving the waterfall view also clears the held frequency, except during a configuration redraw.
