---
kind: alternate
routes:
  main: Main
steps:
- text: Supported external hardware hears a network request while collection or trace recording is active.
  kind: condition
  entities: []
  unattended: true
  contexts:
    main:
      place: phone::requested-networks
- text: The Product retains the requested name and its observation summary.
  kind: product
  entities:
  - entity: requested-network
    effect: creates
    facts:
    - Name
    - Devices
    - Seen
    - Signal
  contexts:
    main:
      place: phone::requested-networks
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/probes/ProbeListActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/data/ProbeLog.kt
---

# Collect the network names nearby devices ask for

## Trigger

Supported external hardware hears a network request while collection or trace recording is active.

## Outcome

The Product retains the requested name and its observation summary.
