---
appliesTo:
- type: capability
  id: classify-signals
- type: capability
  id: check-cell-signs
- type: capability
  id: check-satellite-signs
- type: capability
  id: receive-aircraft
- type: capability
  id: receive-waze-reports
- type: capability
  id: browse-radio
- type: entity
  id: match-history
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/ScanForegroundService.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/data/DetectionEntity.kt
---

# Qualifying observations are recorded in match history

The matched radio path records the strongest classification at most once per address per thirty seconds, after trust and tracker-ignore checks. Cell, satellite, radio and online observations use their source-specific logging paths. GPS tagging determines whether the associated position is retained. All remembered addresses and recorded trace devices remain separate from this log.
