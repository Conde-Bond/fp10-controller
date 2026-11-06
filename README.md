# FP-10 Controller

A single-page remote for the Roland FP-10 digital piano: **transpose** (−6…+5) and **voice** (36 panel voices + 2 hidden ones).
No install, no external dependencies — the whole app is `index.html`.

**Open:** https://conde-bond.github.io/fp10-controller/

## Android (Chrome)
1. Connect the FP-10 in a Bluetooth-MIDI app (tested: *FluidSynth MIDI*) and approve the pairing prompt. You can close the app afterwards.
2. Open the page and tap **Connect (MIDI)**. Allow "control and reprogramme your MIDI devices" when Chrome asks (needed for SysEx).

Also works with a USB cable on any browser with Web MIDI. Chrome's own Web Bluetooth button is included, but most systems
need the OS-level pairing above for the piano to accept commands.

## What it sends
Only Roland SysEx to three addresses: remote enable `01000306`, transpose `01000307` (read back from `01000101`),
tone `01000207`. Everything else is read-only. Not affiliated with Roland.
