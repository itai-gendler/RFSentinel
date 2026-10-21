---
domain: navigation
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/nav/Navigator.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/MapNav.kt
---

# Route

The way to a destination, optionally through stops: up to three proposed routes, then the one being guided, re-planned when the user leaves it, until arrival or Stop. It is kept only while planning or guiding.

## Information kept

- **Destination** — Chosen final place.
- **Stops** — Ordered intermediate places.
- **Path** — The roads it takes, its turns and the lane arrows where the map has them.
- **Estimate** — Distance, time and arrival time, starting from the route's usual driving time and then following how the user really drives.
- **Options** — Avoid tolls, highways or ferries, avoid speed cameras or plate readers, and the known cameras still on it.
- **Progress** — The next turn and its distance, what is left of the route, and whether it is re-routing.

## States

### Preview

Proposed routes are available for selection.

### Guiding

The selected route guides travel.

### Replanning

A replacement route is being requested.
