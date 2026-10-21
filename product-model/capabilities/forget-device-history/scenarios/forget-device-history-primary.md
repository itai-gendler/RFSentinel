---
kind: primary
routes:
  main: Main
steps:
- text: The user confirms Forget device history.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::settings-data
- text: The Product removes nonfavorite remembered addresses and clears remembered cell observations.
  kind: product
  entities:
  - entity: remembered-device
    effect: removes
  - entity: cell-tower
    effect: removes
  actor: user
  contexts:
    main:
      place: phone::settings-data
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/settings/SettingsActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/data/KnownDeviceEntity.kt
---

# Forget device history

## Trigger

The user confirms Forget device history.

## Outcome

The Product removes nonfavorite remembered addresses and clears remembered cell observations.

## Edge cases

- Favorite addresses remain. Names and notes alone do not protect an address from this explicit operation.
