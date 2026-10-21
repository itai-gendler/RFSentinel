---
kind: primary
routes:
  main: Main
steps:
- text: A scheduled cell check receives usable modem information.
  kind: condition
  entities:
  - entity: preferences
    effect: reads
    facts:
    - Detection
    - Cell towers
  unattended: true
  contexts:
    main:
      place: phone::cells
- text: The Product retains cell observations and evaluates warning evidence, allowing for persistence, roaming,
    border context and recent calls.
  kind: product
  entities:
  - entity: cell-tower
    effect: creates
    facts:
    - Identity
    - Serving
    - Signal
    - Seen
    - Position
    - Warning
  contexts:
    main:
      place: phone::cells
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/CellMonitor.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/detect/CellAnalyzer.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/ScanForegroundService.kt
---

# Check cell signs

## Trigger

A scheduled cell check receives usable modem information.

## Outcome

The Product retains cell observations and evaluates warning evidence, allowing for persistence, roaming, border context and recent calls.

## Edge cases

- An unavailable or empty modem response produces no new anomaly.
- Qualifying anomalies use their own thirty-minute repeat window; notification delivery also uses the selected confidence threshold.
- Optional serving-tower change announcements are distinct from anomaly detection.
