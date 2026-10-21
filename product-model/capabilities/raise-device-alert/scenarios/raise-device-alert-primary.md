---
kind: primary
routes:
  main: Main
steps:
- text: A non-tracker observation has a qualifying match and the per-address re-alert interval has elapsed.
  kind: condition
  entities:
  - entity: preferences
    effect: reads
    facts:
    - Alerts
    - Voice
    - Alert mute
    - Snoozed until
  unattended: true
  contexts:
    main:
      place: phone::nearby
- text: The Product delivers the enabled alert outputs for the observation.
  kind: product
  entities:
  - entity: nearby-device
    effect: reads
    facts:
    - Address
    - Evidence
    - Signal
    - Position
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

# Alert about a flagged device

## Trigger

A non-tracker observation has a qualifying match and the per-address re-alert interval has elapsed.

## Outcome

The Product delivers the enabled alert outputs for the observation.

## Edge cases

- Sound and voice honor mute and snooze; vibration follows its own setting.
- Notification permission affects visible Android notifications independently of sound.
