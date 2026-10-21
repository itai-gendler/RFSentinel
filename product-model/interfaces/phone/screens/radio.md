---
entities:
- entity: radio-view
  shows:
  - Mode
  - Frequency
  - Spectrum
- entity: radio-signal
  shows:
  - Frequency
  - Strength
  - Evidence
  - Time
- entity: hardware
  shows:
  - Kind
  - Status
  - Observations
  - Firmware
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/WaterfallActivity.kt
---

# Radio waterfall

The radio waterfall: a live picture of the watched bands from an RTL-SDR or HackRF, one row per sweep, where the user can tune in on one signal.
