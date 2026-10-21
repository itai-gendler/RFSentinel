---
kind: primary
routes:
  main: Main
steps:
- text: The user views the threat bubble while using another application.
  kind: actor
  actor: user
  entities: &id001
  - entity: nearby-device
    effect: reads
    facts:
    - Evidence
    - Following
  contexts:
    main:
      place: phone::floating-views
- text: The Product summarizes current in-range flagged observations, including follower evidence.
  kind: product
  actor: user
  entities: *id001
  contexts:
    main:
      place: phone::floating-views
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/ThreatBubble.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/FloatingMap.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/ScanForegroundService.kt
---

# Monitor the threat bubble

## Trigger

The user is using another application while the threat bubble is selected.

## Outcome

The Product summarizes current in-range flagged observations, including follower evidence.

## Edge cases

- The threat summary clears as observations leave range.
- The floating view hides while RF Sentinel is in the foreground and ends when scanning stops.
