---
title: Week 2
tags:
  - journal
---

# Week 2 — Familiarisation, ArduPilot flash, repo setup

**Period:** _tbd_
**Focus areas:** Drone handling, flight controller firmware, companion computer, documentation

## Summary

We got hands-on with the drone, evaluated which autopilot firmware to use, flashed ArduPilot, prepared the Raspberry Pi as a companion computer, and set up the documentation repository on GitHub Pages.

## What we did

- **Drone handling:** First indoor flights with the drone in its delivered state. Disassembled and reassembled parts of the drone to understand the build.
- **Firmware evaluation:** Investigated whether PX4 is an option for our flight controller. PX4 is not supported on this FC, so we chose **ArduPilot**.
- **Flashed ArduPilot** onto the flight controller.
- **Raspberry Pi setup:** Flashed Raspberry Pi OS (64-bit, Lite — no desktop environment) onto the SD card and configured headless SSH access.
- **Documentation:** Created the GitHub Pages documentation site using MkDocs Material and set up automatic deployment via GitHub Actions.

## Decisions made

| Decision | Reasoning |
|----------|-----------|
| Use ArduPilot as flight controller firmware | PX4 is not supported on the FC delivered with our drone |
| Use Raspberry Pi OS Lite (64-bit) without desktop environment | The Pi acts as a headless companion computer; no GUI needed, lower resource usage |
| Use MkDocs Material for documentation | Markdown-based, integrates well with GitHub Pages, no slide decks or PDF reports required by the project brief |

## Problems

### Resolved

- **Problem:** Drone could not be disarmed.
  **Cause:** ArduPilot pre-arm checks failed because no GPS fix could be acquired indoors.
  **Fix:** Disabled the GPS arming check for indoor testing. To be re-enabled before any outdoor flight.

- **Problem:** Motor mapping was incorrect after the firmware flash.
  **Cause:** ArduPilot uses a different motor numbering convention than Betaflight.
  **Fix:** Set the motor mapping parameters in ArduPilot to match the physical wiring.

- **Problem:** Wobbly flight behaviour.
  **Cause:** Default frame size assumption did not match our 3.5" cinewhoop.
  **Fix:** Set the propeller / frame size to 3.5" in the ArduPilot configuration.

### Still open

- **Problem:** Boot button on the flight controller does not appear to work.
  **Current hypothesis:** Possibly a hardware issue or the bootloader is not configured to react to the button.
  **Next action:** Check if firmware updates can still be applied via the standard procedure (DFU mode); investigate alternative entry into bootloader.

- **Problem:** Drone drifts slightly forward-left when hovering and tilts in the same direction after disarming.
  **Current hypothesis:** Likely an accelerometer / level-horizon calibration issue, or possibly motor mapping / rotation direction. PID tuning may also play a role.
  **Next action:** Redo accelerometer calibration on a level surface, run "Level Horizon" calibration, verify motor order and rotation direction in the motor test, and check logs.

## Artefacts

- ArduPilot parameter file (initial state) — _to be added_
- GitHub Pages documentation: <https://ki-drohnen-ss26.github.io/project-docs/>

## Next week

- [ ] Resolve the forward-left drift via re-calibration and motor test.
- [ ] Verify motor rotation direction and order.
- [ ] First successful stable hover in `STABILIZE` mode.
- [ ] Begin researching MTF-01P configuration via the CP2102 USB-UART adapter.
