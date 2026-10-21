---
kind: alternate
routes:
  main: Main
steps:
- text: The user views the floating map while using another application.
  kind: actor
  actor: user
  entities: &id001
  - entity: nearby-device
    effect: reads
    facts:
    - Evidence
    - Following
    - Position
  - entity: known-camera
    effect: reads
    facts:
    - Position
    - Kind
    - Alerts ignored
  contexts:
    main:
      place: phone::floating-views
- text: The Product shows observed positions and nearby mapped cameras centered on the latest location.
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

# Monitor the floating map

## Trigger

The user is using another application while the mini map is selected.

## Outcome

The Product shows observed positions and nearby mapped cameras centered on the latest location.

## Edge cases

- The view reports waiting when no location is available.
- The floating map uses its own fixed map provider and requests precise location updates while visible.
- The floating view hides while RF Sentinel is in the foreground and ends when scanning stops.
