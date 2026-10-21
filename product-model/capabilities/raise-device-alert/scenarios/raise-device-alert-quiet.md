---
kind: alternate
routes:
  main: Main
steps:
- text: A match is below threshold, list-only, trusted, ignored or within its repeat interval.
  kind: condition
  entities: []
  unattended: true
  contexts:
    main:
      place: phone::nearby
- text: The Product keeps the observation available without issuing another ordinary alert.
  kind: product
  entities:
  - entity: nearby-device
    effect: reads
    facts:
    - Evidence
  contexts:
    main:
      place: phone::nearby
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/ScanForegroundService.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/NotificationHelper.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/AlertPlayer.kt
---

# Stay quiet about a device that may not alert

## Trigger

A match is below threshold, list-only, trusted, ignored or within its repeat interval.

## Outcome

The Product keeps the observation available without issuing another ordinary alert.
