---
kind: primary
routes:
  main: Main
steps:
- text: The user opens the trusted-address list.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::whitelist
- text: The Product shows retained trusted addresses and notes.
  kind: product
  entities:
  - entity: whitelist-entry
    effect: reads
    facts:
    - Address
    - Note
  actor: user
  contexts:
    main:
      place: phone::whitelist
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/whitelist/WhitelistActivity.kt
---

# Browse whitelist

## Trigger

The user opens the trusted-address list.

## Outcome

The Product shows retained trusted addresses and notes.
