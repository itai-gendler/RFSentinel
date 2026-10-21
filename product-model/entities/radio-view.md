---
domain: radio
singleton: true
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/WaterfallActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/sdr/SdrRadio.kt
---

# Radio waterfall

The current receiver view of sweep or selected-frequency measurements.

## Information kept

- **Mode** — Band sweep or tuned frequency.
- **Frequency** — Center frequency while tuned.
- **Spectrum** — Current measured signal power over frequency and time.
