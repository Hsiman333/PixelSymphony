# PixelSymphony

![page views](https://visitor-badge.laobi.icu/badge?page_id=Hsiman333.PixelSymphony)
![GitHub last commit](https://img.shields.io/github/last-commit/Hsiman333/PixelSymphony)
![GitHub repo size](https://img.shields.io/github/repo-size/Hsiman333/PixelSymphony)

A 158-neuron biological connectome that composes music from an image — no samples, no MIDI file, no pre-written song. Load a picture and a simulated neural network (sensory → vision → memory → ideas → key/harmony/rhythm → motor) listens to its color, brightness, edges and texture, and plays music that emerges from what it "sees."

**Live demo: https://hsiman333.github.io/PixelSymphony/**

## How to use

1. Open the live demo (or `index.html` locally in a browser).
2. Load an image (drag & drop, or the LOAD IMAGE button).
3. Press **START PERFORMANCE**, or **TRAIN** first to fast-forward the network through a few simulated loops so the key/motifs/timbre mature before real-time playback picks up.
4. Optional: pick a **GENRE** to bias the network toward that style's key, rhythm feel, instrumentation and song structure, and a **SONG FORM** (full arc with an ending, or an endless chorus loop).
5. **RECORD** captures the live performance and saves it as an audio file when you stop.

## What it's doing

- **Emergent composition** — notes aren't scripted; they come from simulated neurons firing based on accumulated "charge," with the image driving sensory input the whole time.
- **Genre-aware song structure** — each genre gets its own real arrangement (e.g. Jazz: Intro→Head→Solo→Head→Outro; Electronic: Intro→Build→Drop→Breakdown→Drop→Outro; Classical: no drum kit at all), not one generic shape for every style.
- **Real sampled instruments** — genres where it matters (jazz sax, classical strings, blues guitar, R&B/lo-fi Rhodes, piano everywhere) use actual recorded instrument samples via a soundfont, not oscillators; electronic/rap stay synthesized on purpose.
- **Rule-based note selection** — melody and bass follow a weighted chord-tone-priority algorithm (root/3rd/5th/7th, interval discipline, strong-beat resolution) instead of picking randomly, so it stays in key and reads as an actual line.
- **Live readouts** — network layer activity, motif memory (recognizes and reuses recurring melodic phrases), and a per-section memory panel showing what's built up in each part of the song so far.

## Tech

Single self-contained HTML file. Web Audio API for synthesis/effects (reverb, delay, compressor, limiter), Canvas for the neural visualization, [soundfont-player](https://github.com/danigb/soundfont-player) for the real sampled instruments (loaded from a CDN, with a graceful fallback to synthesis if that fails). No build step, no server.
