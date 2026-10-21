---
kind: primary
routes:
  main: Main
steps:
- text: The user searches the requested-network list or selects a name.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::requested-networks
- text: The Product shows the observed names, requesting addresses, times and signals.
  kind: product
  entities:
  - entity: requested-network
    effect: reads
    facts:
    - Name
    - Devices
    - Seen
    - Signal
  actor: user
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

# Browse requested networks

## Trigger

The user searches the requested-network list or selects a name.

## Outcome

The Product shows the observed names, requesting addresses, times and signals.
