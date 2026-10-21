---
kind: primary
routes:
  main: Main
steps:
- text: The user confirms clearing the requested-name list.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::requested-networks
- text: The Product removes the collected request summaries.
  kind: product
  entities:
  - entity: requested-network
    effect: removes
  actor: user
  contexts:
    main:
      place: phone::requested-networks
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/probes/ProbeListActivity.kt
---

# Clear requested networks

## Trigger

The user confirms clearing the requested-name list.

## Outcome

The Product removes the collected request summaries.
