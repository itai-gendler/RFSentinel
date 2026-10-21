---
kind: alternate
routes:
  main: Main
steps:
- text: The same eligible observation appears at three sufficiently separated locations within two hours and meets
    the configured duration and distance.
  kind: condition
  entities: []
  unattended: true
  contexts:
    main:
      place: phone::nearby
- text: The Product marks it as potentially following even though it was absent between locations.
  kind: product
  entities:
  - entity: nearby-device
    effect: changes
    facts:
    - Following
  contexts:
    main:
      place: phone::nearby
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/ScanForegroundService.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/DeviceRegistry.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/PlaceFollow.kt
---

# Warn about a device that keeps turning up

## Trigger

The same eligible observation appears at three sufficiently separated locations within two hours and meets the configured duration and distance.

## Outcome

The Product marks it as potentially following even though it was absent between locations.

## Edge cases

- Separate locations are at least three hundred meters apart, and their maximum pairwise distance must meet the configured distance.
- The duration threshold still applies when observations have gaps.
