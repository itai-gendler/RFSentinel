---
entities:
- entity: aircraft
  shows:
  - Identification
  - Position
  - Source
  - Evidence
  - Time
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/AircraftActivity.kt
---

# Aircraft

The aircraft from the online ADS-B feeds or the user's own receiver, with the police and circling evidence for each flagged one.
