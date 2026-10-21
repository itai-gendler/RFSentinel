---
kind: alternate
routes:
  main: Main
steps:
- text: The user chooses the trace format and the available all-device or flagged-only scope.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::traces
- text: The Product supplies the saved travel path and device information in the requested format.
  kind: product
  entities:
  - entity: trace
    effect: reads
    facts:
    - Name
    - Times
    - Route
    - Devices
    - Counts
  actor: user
  contexts:
    main:
      place: phone::traces
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/Exporter.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/DeviceExport.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/TripExport.kt
---

# Export a recorded trace

## Trigger

The user chooses the trace format and the available all-device or flagged-only scope.

## Outcome

The Product supplies the saved travel path and device information in the requested format.
