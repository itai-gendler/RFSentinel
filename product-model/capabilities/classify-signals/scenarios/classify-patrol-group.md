---
kind: alternate
routes:
  main: Main
steps:
- text: "Two or more kinds of police-type gear are heard together: their signals rise and fall together (correlation of at least 0.6 over at least 8 seconds), or, while parked, they turned up within 30 seconds of each other."
  kind: condition
  unattended: true
  entities: []
  contexts:
    main:
      place: phone::nearby
- text: The Product flags them as a possible police vehicle, scored 24 plus 12 for each kind of gear, 10 more when they move together, at most 88; the group never strengthens the matches it was built from.
  kind: product
  entities:
  - entity: nearby-device
    effect: changes
    facts:
    - Evidence
  contexts:
    main:
      place: phone::nearby
references:
- kind: spec
  role: intent
  target: docs/SIGNATURES.md
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/detect/PatrolCluster.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/DeviceRegistry.kt
---

# Group gear into a possible patrol vehicle

## Trigger

Two or more kinds of police-type gear are heard together: their signals rise and fall together (correlation of at least 0.6 over at least 8 seconds), or, while parked, they turned up within 30 seconds of each other.

## Outcome

The Product flags them as a possible police vehicle, scored 24 plus 12 for each kind of gear, 10 more when they move together, at most 88; the group never strengthens the matches it was built from.

## Edge cases

- Printers, breath-screening devices and vehicle interface modules only add to a group; it needs a police-specific role, or both a two-way radio and a vehicle cellular router.
- One flat signal beside a moving signal, or too little overlap, does not form a group.
- Trusted addresses are excluded from the group.
