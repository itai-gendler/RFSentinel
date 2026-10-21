---
kind: alternate
routes:
  main: Main
steps:
- text: A device with a random address appears, and exactly one device with the same advert fingerprint went silent 1.5 to 30 seconds earlier.
  kind: condition
  unattended: true
  entities: []
  contexts:
    main:
      place: phone::nearby
- text: The Product links the new address to the old one and carries over its matches five points lower, how long it has been heard, where it was heard and any follower warning.
  kind: product
  entities:
  - entity: nearby-device
    effect: changes
    facts:
    - Linked address
    - Evidence
    - Seen
    - Following
  contexts:
    main:
      place: phone::nearby
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/DeviceRegistry.kt
---

# Carry evidence across a likely address change

## Trigger

A device with a random address appears, and exactly one device with the same advert fingerprint (names, service IDs, payload sizes, transmit power, connectable) went silent 1.5 to 30 seconds earlier.

## Outcome

The Product treats both addresses as the same device: its matches carry over five points lower, with the old address in their evidence, and the follower check continues from its time with the user and where it was heard, without warning again.

## Edge cases

- Two or more matching candidates, such as several identical earbuds, leave the addresses unlinked.
- A continuation describes a software inference, not a verified identity.
