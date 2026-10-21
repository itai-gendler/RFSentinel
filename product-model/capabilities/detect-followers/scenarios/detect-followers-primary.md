---
kind: primary
routes:
  main: Main
steps:
- text: An eligible flagged observation has remained with the phone for the configured duration and displacement.
  kind: condition
  entities:
  - entity: preferences
    effect: reads
    facts:
    - Follower alerts
    - Tracker warnings paused until
  unattended: true
  contexts:
    main:
      place: phone::nearby
- text: The Product marks the observation as potentially following and delivers a follower warning.
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

# Warn about a device moving with the user

## Trigger

An eligible flagged observation has remained with the phone for the configured duration and displacement.

## Outcome

The Product marks the observation as potentially following and delivers a follower warning.

## Edge cases

- Trackers nearby alone do not generate the ordinary arrival alert.
- A global tracker pause affects tracker-follow warnings, not all equipment categories.
- Continuous following requires at least three path samples and the greatest distance from the first sample to meet the configured distance; distance traveled around a loop is not added together.
