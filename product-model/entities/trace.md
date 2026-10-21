---
domain: recorded-traces
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/data/Trips.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/TripRecorder.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/TripsActivity.kt
---

# Recorded trace

A recorded journey with the phone route and devices heard along it.

## Information kept

- **Name** — User-facing trace name.
- **Times** — Recording start and end.
- **Route** — Location points and total traveled distance.
- **Devices** — Encountered addresses with strongest signal, position, classifications and requested networks.
- **Counts** — GPS points, devices and flagged devices.

## States

### Recording

Route and device observations are being accumulated.

### Saved

Recording has finished and the trace can be reviewed.
