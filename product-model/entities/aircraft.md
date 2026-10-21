---
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/online/PoliceAircraft.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/online/OnlineWatch.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/AircraftActivity.kt
---

# Aircraft

An ADS-B aircraft report from an optional feed or local receiver.

## Information kept

- **Identification** — Broadcast address, callsign and registry match when present.
- **Position** — Reported position, altitude, speed and heading.
- **Source** — Online feed or local ADS-B reception.
- **Evidence** — Registry or low-circling inference with confidence.
- **Time** — Freshness of the report.
