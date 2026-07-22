# JC-808 Rhythm Composer

A drum machine and synthesiser that runs entirely in the browser. Every sound is
synthesised live with the Web Audio API — no samples, no audio libraries, no
build step.

**Live:** [JC-808](https://jc-808.vercel.app/)

## What's in it

**Rhythm section**
- Twelve analogue-modelled voices: bass drum, snare, three toms, rim shot, hand
  clap, cowbell, closed/open hat, cymbal, maracas. The hats and cymbal use the
  six-square-wave metal bank of the original machines, and the closed hat chokes
  the open hat the way the hardware does.
- 16-step sequencer with a global accent lane, swing, and adjustable pattern
  length (1–16 steps) for odd meters.
- Four pattern banks with chaining (A→B→C→D) and shift-click copy.
- Per-voice level, tune and decay; mute and solo on every track.
- Eight presets, a pattern randomiser, and multi-level undo.

**Synthesiser**
- Two detuned oscillators plus a sub, resonant low-pass filter with envelope
  amount, full ADSR, poly or mono.
- Arpeggiator locked to the sequencer clock — up / down / up-down / random,
  straight and triplet rates, up to four octaves, latch.
- Tempo-synced delay and a generated plate reverb.

**Everything else**
- Tap tempo, master drive and compression, oscilloscope output.
- Patterns persist to `localStorage` and encode into a share link.
- **WAV export** — renders the pattern offline and downloads it.

## Controls

| Key | Action |
| --- | --- |
| `Space` | Play / stop |
| `Esc` | All notes off |
| `1` … `=` | Trigger the twelve drum voices |
| `A W S E D F T G Y H U J K` | Play the synth |
| `Z` / `X` | Octave down / up |

Knobs respond to drag, scroll wheel, and arrow keys; shift for fine adjustment,
double-click to reset.

## Running locally

No dependencies and no build. Any static server works:

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

Opening `index.html` directly from the filesystem also works.

## Deploying

It's three static files, so Vercel needs no configuration — import the repo and
deploy with the framework preset set to **Other** and no build command.

## Notes

The design takes its cues from classic Roland drum machines, but this is an
original implementation with no affiliation to or endorsement by Roland.

Built by [Jake Cushway](https://www.jakecushway.ca).
