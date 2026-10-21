---
kind: primary
routes:
  main: Main
steps:
- text: The active GPS receiver supplies satellite observations.
  kind: condition
  entities:
  - entity: preferences
    effect: reads
    facts:
    - Detection
  unattended: true
  contexts:
    main:
      place: phone::satellites
- text: The Product updates satellite information and any supported warning evidence.
  kind: product
  entities:
  - entity: satellite-status
    effect: changes
    facts:
    - Satellites
    - Signal
    - Warning
  contexts:
    main:
      place: phone::satellites
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/GnssWatch.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/detect/GnssAnalyzer.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/ScanForegroundService.kt
---

# Check satellite signs

## Trigger

The active GPS receiver supplies satellite observations.

## Outcome

The Product updates satellite information and any supported warning evidence.

## Edge cases

- Warnings are evidence of unusual observations, not proof of interference or its source.
