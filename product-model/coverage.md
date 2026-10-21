---
scope: The Android app's scanning, evidence, alerts, history, maps, navigation, Android Auto, optional sources and receiver workflows.
method: Static inspection of source and supporting documentation at the pinned upstream revision.
covered:
- description: Scan service, evidence pipeline and main screen
  paths:
  - app/src/main/java/com/rfsentinel/app/service/
  - app/src/main/java/com/rfsentinel/app/detect/
  - app/src/main/java/com/rfsentinel/app/MainActivity.kt
- description: Local persistence and history
  paths:
  - app/src/main/java/com/rfsentinel/app/data/
  - app/src/main/java/com/rfsentinel/app/history/
- description: Watchlist, whitelist and requested-network lists
  paths:
  - app/src/main/java/com/rfsentinel/app/oui/
  - app/src/main/java/com/rfsentinel/app/ouilist/
  - app/src/main/java/com/rfsentinel/app/whitelist/
  - app/src/main/java/com/rfsentinel/app/probes/
- description: Phone screens, setup and settings
  paths:
  - app/src/main/java/com/rfsentinel/app/ui/
  - app/src/main/java/com/rfsentinel/app/settings/
- description: Android Auto car app and scan triggers
  paths:
  - app/src/main/java/com/rfsentinel/app/car/
  - app/src/main/java/com/rfsentinel/app/receiver/
- description: Known cameras and navigation
  paths:
  - app/src/main/java/com/rfsentinel/app/alpr/
  - app/src/main/java/com/rfsentinel/app/nav/
- description: Online aircraft and Waze sources
  paths:
  - app/src/main/java/com/rfsentinel/app/online/
- description: External receivers, firmware and frame recording
  paths:
  - app/src/main/java/com/rfsentinel/app/esp/EspBoards.kt
  - app/src/main/java/com/rfsentinel/app/esp/EspReader.kt
  - app/src/main/java/com/rfsentinel/app/esp/EspReports.kt
  - app/src/main/java/com/rfsentinel/app/esp/HeardBy.kt
  - app/src/main/java/com/rfsentinel/app/esp/OuiSpyBle.kt
  - app/src/main/java/com/rfsentinel/app/usb/UsbWifi.kt
  - app/src/main/java/com/rfsentinel/app/usb/PcapRecorder.kt
  - app/src/main/java/com/rfsentinel/app/usb/Firmware.kt
  - app/src/main/java/com/rfsentinel/app/usb/FirmwarePrompt.kt
  - app/src/main/java/com/rfsentinel/app/sdr/
- description: Sharing, export, backups, permissions, alert sound and updates
  paths:
  - app/src/main/java/com/rfsentinel/app/util/
exclusions:
- description: Build, release, website generation and asset-generation infrastructure
  paths:
  - gradle/
  - tools/
  - .github/
  - app/build.gradle.kts
- description: Resources, bundled data files, styling and map engines of the two build flavors
  paths:
  - app/src/main/res/
  - app/src/main/assets/
  - app/src/foss/
  - app/src/full/
- description: USB WiFi chip drivers, register tables, serial transport and protocol decoding
  paths:
  - app/src/main/java/com/rfsentinel/app/usb/Ar9271Monitor.kt
  - app/src/main/java/com/rfsentinel/app/usb/Ar9271Tables.kt
  - app/src/main/java/com/rfsentinel/app/usb/BulkRx.kt
  - app/src/main/java/com/rfsentinel/app/usb/MonitorFrames.kt
  - app/src/main/java/com/rfsentinel/app/usb/Mt7612uMonitor.kt
  - app/src/main/java/com/rfsentinel/app/usb/Mt7921uMonitor.kt
  - app/src/main/java/com/rfsentinel/app/usb/Rt3070Monitor.kt
  - app/src/main/java/com/rfsentinel/app/usb/Rtl8187Monitor.kt
  - app/src/main/java/com/rfsentinel/app/usb/Rtl8812auMonitor.kt
  - app/src/main/java/com/rfsentinel/app/usb/Rtl8812auTables.kt
  - app/src/main/java/com/rfsentinel/app/usb/Rtl8814auMonitor.kt
  - app/src/main/java/com/rfsentinel/app/usb/Rtl8814auTables.kt
  - app/src/main/java/com/rfsentinel/app/usb/Rtl8821auMonitor.kt
  - app/src/main/java/com/rfsentinel/app/usb/Rtl8821auTables.kt
  - app/src/main/java/com/rfsentinel/app/usb/Rtl8822bTables.kt
  - app/src/main/java/com/rfsentinel/app/usb/Rtl8822buMonitor.kt
  - app/src/main/java/com/rfsentinel/app/esp/SerialPort.kt
  - app/src/main/java/com/rfsentinel/app/esp/OuiSpyBleProtocol.kt
  - app/src/main/proto/
- description: Unit tests and their fixtures, read as evidence only
  paths:
  - app/src/test/
unmapped:
- description: Android Auto media-style screen for cars that run the GitHub build
  paths:
  - app/src/main/java/com/rfsentinel/app/car/RFSentinelMediaService.kt
- description: WiFi deauth attack, evil-twin probe response and probe fingerprint analysis from a USB WiFi adapter
  paths:
  - app/src/main/java/com/rfsentinel/app/usb/DeauthWatch.kt
  - app/src/main/java/com/rfsentinel/app/usb/KarmaWatch.kt
  - app/src/main/java/com/rfsentinel/app/usb/ProbeIntel.kt
- description: European V2X emergency vehicle reports from an ESP32-C5 board
  paths:
  - app/src/main/java/com/rfsentinel/app/esp/V2x.kt
- description: Antenna comparison check for USB adapters
  paths:
  - app/src/main/java/com/rfsentinel/app/ui/AntennaCheckActivity.kt
  - app/src/main/java/com/rfsentinel/app/usb/AntennaCheck.kt
- description: Frequency-name import and RadioReference lookup
  paths:
  - app/src/main/java/com/rfsentinel/app/sdr/FreqNames.kt
  - app/src/main/java/com/rfsentinel/app/sdr/RadioReference.kt
- description: Crash log and USB adapter log export
  paths:
  - app/src/main/java/com/rfsentinel/app/util/CrashLog.kt
- description: Handing a destination to another navigation app
  paths:
  - app/src/main/java/com/rfsentinel/app/nav/HandOff.kt
- description: Waze direct account reset on the Waze status screen
  paths:
  - app/src/main/java/com/rfsentinel/app/ui/WazeStatusActivity.kt
- description: The project website and store listing
  paths:
  - site/
  - docs/
  - fastlane/
limitations: []
---

# Coverage
