---
id: rfsentinel
summary: A free, open-source BLE and WiFi police scanner for Android that passively flags surveillance equipment, trackers, drones and fake cell tower signs.
languages:
- en
limitations:
- RF Sentinel only listens; it never connects to, transmits to or jams the devices it reports.
- A match is a signature and a warning sign is a heuristic; neither identifies a person, an owner or an intent.
- The phone's own WiFi scan sees access points only; WiFi client devices are seen only through a supported USB adapter or ESP32 board.
- Signal strength gives a rough distance and the map a likely position, never a fix or a direction.
- Detections, history and settings stay on the phone, with no account or cloud; they leave it only when the user exports or shares them.
references:
- kind: doc
  role: intent
  target: README.md
- kind: spec
  role: intent
  target: docs/SIGNATURES.md
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/ScanForegroundService.kt
---

# RF Sentinel

RF Sentinel is an Android app that lists the Bluetooth LE and WiFi devices around the phone and flags law-enforcement and surveillance equipment, trackers that follow the user, drones and fake cell tower signs from the signals they already broadcast. Every match shows its evidence, source and confidence. It warns as the user approaches mapped plate-reader and speed cameras, records traces and history for later review, and navigates. Optional ESP32 boards, USB WiFi adapters and SDR receivers, online aircraft and Waze reports, and Android Auto extend it.

## Intent

RF Sentinel is provided for awareness, research and personal privacy, as a free, open-source app with no root, no account, no subscription and no analytics. It passively detects body cameras, plate readers, patrol vehicles, drones, trackers following the user, camera glasses and fake cell tower signs from the signals they already broadcast, and shows why each one is flagged. A detection indicates that a device with a given signature is nearby; it is not proof of who is present or what they are doing.
