# The Resonant Voice

A 30-day, 15–30 minute daily program for building a deeper, clearer, more fluent speaking voice — phonetics-based drills, breath and resonance work, and fluency techniques for stutter-free, authoritative delivery.

**Live:** https://orca5.github.io/resonant-voice/

## What's here

Single self-contained `index.html` — no build step, no dependencies beyond three Google Fonts and the browser's own Web APIs. Two views, switched by a tab at the top:

- **30-Day Program** — four weeks (Foundation → Resonance → Fluency → Delivery), each day broken into warm-up, phonetic drill, fluency practice, an application task, and a reflection prompt. Every target word has a click-to-hear pronunciation button (Web Speech `speechSynthesis`, tuned deeper and slower). Progress checkboxes persist locally per browser (`localStorage`).
- **Live Coach** — real-time mic-based feedback while you read a passage: pace (via `SpeechRecognition`, Chrome only), pitch and pitch range (autocorrelation on the raw mic signal via `AudioContext`/`AnalyserNode`), pauses, filler words, volume. Ends each session with objective feedback rules and, for the five locked **checkpoint** readings (Day 1 / 7 / 14 / 21 / 30, all reading the same fixed passage), a week-over-week comparison table.

Everything computed from the microphone runs locally in the page — nothing is uploaded. The only exception is Chrome's built-in speech recognition, which (like any Chrome dictation feature) sends audio to Google to produce a transcript; that's disclosed in the page itself.

## Running it locally

Just open `index.html` in a browser. The Live Coach's microphone features need a real `http(s)://` origin (or `file://` in Chrome) to get permission properly — they won't work embedded in an iframe.

## Deploying

This repo is served as-is via GitHub Pages from the `main` branch root — see **Settings → Pages**. To update the live site, edit `index.html` and push to `main`; Pages rebuilds automatically (usually live within a minute or two).

## Limits, on purpose

No pronunciation-accuracy scoring (can't tell you if a specific phoneme landed right), no server, no accounts, no tracking. The Live Coach's checkpoint lock picks the right passage but can't verify you actually read it — the comparison is only as honest as your own consistency. See the in-page notes on each tab for the rest.
