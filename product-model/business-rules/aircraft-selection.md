---
appliesTo:
- type: entity
  id: aircraft
  effect: creates
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/online/OnlineWatch.kt
permits:
- unattended: true
  when:
  - entity: preferences
    fact: Aircraft enabled
    is: true
---

# Aircraft are reported only while Police aircraft is on

The Police aircraft category is off by default. While it is on and a scan runs, the online ADS-B feeds are asked about once a minute with a position rounded to about 1 km, and an RTL-SDR set up as an ADS-B receiver adds the aircraft it hears itself; with the online feeds switched off, nothing leaves the phone.
