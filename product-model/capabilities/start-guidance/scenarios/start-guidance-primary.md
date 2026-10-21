---
kind: primary
routes:
  main: Main
steps:
- text: The user starts the selected proposed route.
  kind: actor
  entities:
  - entity: route
    effect: reads
    facts: []
  actor: user
  contexts:
    main:
      place: phone::map
- text: The Product begins guidance and records the destination among recent places.
  kind: product
  entities:
  - entity: route
    effect: changes
    from: Preview
    to: Guiding
    facts:
    - Progress
  - entity: place
    effect: changes
    facts:
    - Saved as
  actor: user
  contexts:
    main:
      place: phone::map
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/MapNav.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/nav/Navigator.kt
---

# Start guidance

## Trigger

The user starts the selected proposed route.

## Outcome

The Product begins guidance and records the destination among recent places.

## Edge cases

- If enabled, guidance starts scanning when required scanning access is available; guidance does not wait for scanning.
