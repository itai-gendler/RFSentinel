---
domain: history
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/data/KnownDeviceEntity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/DeviceHistoryImport.kt
---

# Remembered device

Long-term local memory of a radio address, available when it is no longer nearby.

## Information kept

- **Address** — The radio address being remembered.
- **Name** — Last known broadcast name.
- **Vendor** — Last known maker.
- **Type** — Last known device class.
- **First seen** — Earliest recorded sighting.
- **Last seen** — Most recent recorded sighting.
- **Sessions** — How many separate scans heard it.
- **Sightings** — How many times it was heard, counted at most once a minute while scanning; not a count of broadcasts.
- **Favorite** — Whether it is starred.
- **Own name** — A name supplied by the user.
- **Note** — A user-supplied observation.
