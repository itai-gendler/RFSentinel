---
appliesTo:
- type: entity
  id: radio-view
- type: entity
  id: radio-signal
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/WaterfallActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/sdr/SdrRadio.kt
---

# Tuned inspection pauses band-sweep detection

Holding one frequency changes the receiver to a live tuned view. Returning to sweep or leaving the waterfall releases that frequency and restores sweep detection.
