---
kind: primary
routes:
  main: Main
steps:
- text: A configured, unpaused source check is due while scanning.
  kind: condition
  entities:
  - entity: preferences
    effect: reads
    facts:
    - Detection
  unattended: true
  contexts:
    main:
      place: phone::waze
- text: The Product refreshes current reports and records the request result.
  kind: product
  entities:
  - entity: waze-report
    effect: creates
    facts:
    - Type
    - Position
    - Age
    - Confirmations
    - Relevance
    - Confidence
    - Level
    - Source
  - entity: waze-status
    effect: changes
    facts:
    - Checks
    - Status
  contexts:
    main:
      place: phone::waze
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/online/WazeWatch.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/online/WazePolice.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/ScanForegroundService.kt
---

# Receive Waze reports

## Trigger

A configured, unpaused source check is due while scanning.

## Outcome

The Product refreshes current reports and records the request result.

## Edge cases

- Failed checks expose an error; old reports are eventually removed after the source freshness window.
- A missing position delays the request rather than inventing an origin.

## Decision points

### Selected report source

Which configured source supplies this check?

- OpenWeb Ninja selected → use the configured API key and the source interval, then evaluate the returned crowd reports.
- Waze direct selected → use the acknowledged direct source and its retained anonymous service account, then evaluate the returned crowd reports.
