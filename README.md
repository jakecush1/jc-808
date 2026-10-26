# JC-808 Rhythm Composer

A drum machine and synthesiser that runs entirely in the browser. Every sound is
synthesised live with the Web Audio API — no samples, no audio libraries.

**Live:** [JC-808](https://jc-808.vercel.app/)

> **This repo is a built copy.** The JC-808 is developed inside the
> [Room 808 bedroom studio](https://github.com/jakecush1/bedroom-studio)
> (`src/tools/jc808`), where it is one of the machines in the room. Running
> `./update.sh` there rebuilds this standalone page and pushes it here, so
> **edit the JC-808 in bedroom-studio, not in this repo** — changes made here
> will be overwritten on the next publish.

## What's in it

**Rhythm section**
- Twelve analogue-modelled voices: bass drum, snare, three toms, rim shot, hand
  clap, cowbell, closed/open hat, cymbal, maracas. The hats and cymbal use the
  six-square-wave metal bank of the original machines, and the closed hat chokes
  the open hat the way the hardware does.
- 16-step sequencer with a global accent lane, swing, and adjustable pattern
  length (1–16 steps) for odd meters.
- Per-step **echo and reverb**: set "Click paints" to Echo or Reverb and click a
  hit to send it to the effect (shift-click / alt-click from any mode). Each
  voice and step is separate and everything is dry by default; the Echo and
  Reverb faders set how much a painted step sends.
- Four pattern banks with chaining (A→B→C→D) and shift-click copy.
- Per-voice level, tune and decay; mute and solo on every track.
- Eight presets, a pattern randomiser, and multi-level undo.

**Synthesiser**
- Two lanes, Bass and Lead, each with its own patch and a looping recorder:
  press Rec and play the keys, and the take loops under the drums. Lanes have
  their own loop length and quantize, and export to MIDI.
- Two detuned oscillators plus a sub, resonant low-pass filter with envelope
  amount, full ADSR, poly or mono, and fourteen patch presets (basses, leads,
  pads, bell, organ, arps).
- Arpeggiator locked to the sequencer clock — up / down / up-down / random,
  straight and triplet rates, up to four octaves, latch. Arp notes are written
  to the lane when recording.
- Tempo-synced delay and a generated plate reverb.

**Everything else**
- Vertical mixing-desk faders for every control (shift-drag for fine, wheel to
  nudge, double-click to reset).
- Tap tempo, master drive and compression, oscilloscope output.
- Sequencer clock in a Web Worker, so the beat holds steady in a background tab.
- Patterns save to the browser and to the share link; WAV export renders the
  pattern (or the chain) offline with both synth lanes.

## Files

`index.html` and `assets/` are the Vite build output of
`standalone/jc808` in bedroom-studio. Deploy the repo root as a static site.
