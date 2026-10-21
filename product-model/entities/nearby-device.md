---
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/DeviceRegistry.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/DeviceDetailActivity.kt
relations:
- entity: drone
  verb: has remote ID information
  cardinality: one-to-one
- entity: remembered-device
  verb: has remembered address
  cardinality: one-to-one
---

# Nearby device

A currently retained radio observation, with inferred type and matching evidence.

## Information kept

- **Address** — Observed Bluetooth or WiFi address.
- **Name** — Broadcast name or network name.
- **Vendor** — Registry or advertisement manufacturer attribution.
- **Type** — Inferred device class.
- **Sources** — Phone or external receiver and radio technology.
- **Signal** — Current smoothed signal, strongest reading, trend and rough distance.
- **Evidence** — Matches with category, label, score, tier, observed reason and cited source.
- **Seen** — First and latest observation and packet count in this session.
- **Decoded data** — Broadcast fields, raw advertisement and fingerprint clues.
- **Position** — Broadcast position, estimated location with uncertainty, or strongest-signal observation location.
- **Following** — Whether a movement-based follower condition was met.
- **Linked address** — Best-effort continuation under a changed address.
- **Locate active** — Whether proximity audio is following this observation.

## States

### Heard

Recently heard within the live range window.

### Stale

Retained briefly after it is no longer in range.
