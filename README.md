# FP-10 Controller

A single-page remote for the Roland FP-10 digital piano — no install, no external dependencies (the whole app is `index.html`).

**Open:** https://conde-bond.github.io/fp10-controller/

- **Settings:** master volume, key touch, master tuning (415.3–466.2 Hz), brilliance, keyboard transpose (−6…+5), ambience
- **Tones:** Single / Split / Dual / Twin, 36 voices + 2 hidden ones, split point, balances, octave shifts, twin pair/individual

## Android (Chrome)
1. Connect the FP-10 in a Bluetooth-MIDI app (tested: *FluidSynth MIDI*) and approve the pairing prompt. You can close the app afterwards.
2. Open the page and tap **Connect (MIDI)**. Allow "control and reprogramme your MIDI devices" when Chrome asks (needed for SysEx).

## Windows PC
Browsers on Windows can't make the Bluetooth connection the FP-10 needs (it only answers on a link that was paired during
that same connection). A small local helper does that and serves this page at `http://localhost:8710`; the **Connect (PC)**
button talks to it. A USB cable works with **Connect (MIDI)** in any browser with Web MIDI.

## What it sends
Roland SysEx only, to a fixed allow-list of settings addresses in the `01000200` block plus transpose (`01000307`) and
remote enable (`01000306`); everything else is read-only. Not affiliated with Roland.
