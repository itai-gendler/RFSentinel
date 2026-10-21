---
domain: known-cameras
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/alpr/Cctv.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/MapShared.kt
---

# CCTV camera

A mapped surveillance camera shown as contextual map data.

## Information kept

- **Position** — Mapped coordinates and map reference.
- **Description** — Camera type and operator information.
- **Visibility** — Public, outdoor private or indoor classification.
- **View area** — Mapped facing direction and viewing angle.
