---
kind: alternate
routes:
  main: Main
steps:
- text: A flagged device qualifies for an alert while the phone is connected to Android Auto.
  kind: condition
  unattended: true
  entities:
  - entity: preferences
    effect: reads
    facts:
    - Snoozed until
  contexts:
    main:
      place: car
- text: The Product posts the alert as a message from RF Sentinel in the car, saying what it is, how sure the match is, about how far away and its signal, instead of a phone notification.
  kind: product
  entities:
  - entity: nearby-device
    effect: reads
    facts:
    - Evidence
    - Signal
    - Position
  contexts:
    main:
      place: car
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/NotificationHelper.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/CarMessages.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/receiver/CarMessageReceiver.kt
---

# Alert in the car

## Trigger

A flagged device qualifies for an alert while the phone is connected to Android Auto.

## Outcome

The alert arrives as a message from RF Sentinel that the car shows and can read aloud: what it is, how sure, about how far and its signal.

## Edge cases

- While alerts are snoozed, no message is posted.
- In Discreet mode the message says only that there is a new alert.
- Replying "mute" snoozes alerts and replying "ignore" stops alerting about that device.
