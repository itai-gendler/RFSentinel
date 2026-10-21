---
singleton: true
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/Prefs.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/settings/SettingsActivity.kt
---

# Settings

Choices kept for this installation and applied to subsequent operations.

## Information kept

- **Setup complete** — Whether the initial setup has been finished.
- **General** — Discreet mode, screen behavior, rotation and automatic update checks.
- **Appearance** — Selected theme and appearance preferences.
- **Scanning** — Bluetooth and WiFi enablement, intensity, interval, background behavior and live-list lifetimes.
- **Auto start** — Boot scanning, car scanning and selected paired car devices.
- **Detection** — Enabled equipment categories, presets, tracker exclusions and optional online source choices.
- **Alerts** — Threshold, sound, vibration, proximity beeps, sound style and re-alert interval.
- **Voice** — Voice, rate, loudness, short phrases and car speech preferences.
- **Floating views** — Whether the threat bubble and mini map are shown while scanning.
- **Follower alerts** — Whether movement-based warnings are enabled, with time and distance thresholds.
- **Navigation** — Route preferences, guidance speech and whether guidance starts scanning.
- **Map** — Provider, layers, following behavior, speed and distance presentation.
- **Known cameras** — Automatic downloads, radius, camera warnings and CCTV visibility.
- **Cell towers** — Serving-tower change announcements.
- **External hardware** — Selected board, relay mode, adapter choices and requested-network collection.
- **Radio** — Sensitivity, built-in and own bands, ranges never to report, frequencies to watch, cellular transmitters, closer or moving-away call-outs and ADS-B reception.
- **Location** — GPS tagging, precise placement and automatic trace recording.
- **Data** — Retention period and live-export destination and enablement.
- **Alert mute** — Whether alert sound and speech remain muted.
- **Snoozed until** — Expiry of temporary alert sound and speech suppression.
- **Tracker warnings paused until** — Expiry of the global tracker-follow pause.
- **Aircraft enabled** — Whether aircraft observations are enabled.
- **Waze ready** — The report category and selected source setup and acknowledgment are enabled.
- **Follower warnings enabled** — Whether movement-based follower checks are enabled.
- **Cell checks enabled** — Whether the cell-anomaly category is enabled.
- **Satellite checks enabled** — Whether the satellite-anomaly category is enabled.
- **Frame collection enabled** — Requested-network collection is selected, or an active trace requires it.
- **Online aircraft enabled** — Whether the optional online aircraft source is enabled.
