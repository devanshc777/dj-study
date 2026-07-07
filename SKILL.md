---
name: dj-study
description: Study DJ technique from YouTube — pull tutorial/remix-breakdown transcripts via yt-vault, distill them into technique notes, and turn described transitions into reproducible dj-holo settings. Use when the user wants to "learn this mix", "watch this DJ tutorial", "break down this remix/transition", "study a set", or build DJ knowledge notes on their music path.
---

# dj-study — DJ tutorials & remix breakdowns → notes → practice

Turns DJ videos into (1) technique notes in the vault and (2) concrete practice recipes for dj-holo.

## Pipeline

1. **Get the words** — fetch transcript with yt-vault (see `yt-vault` skill for full flags):
   ```bash
   cd "C:/Dev/python/projects/yt-vault" && export PYTHONIOENCODING=utf-8 && \
     uv run python yt.py get "<URL>"        # or: grab "dj transition tutorial" -n 3
   ```
   Read the saved markdown, work from it.

2. **Distill** — extract only actionable technique: BPM relationships, when EQs move (e.g. "bass swap on the 32nd bar"), loop/cue usage, crossfade length, FX moments. Skip filler.

3. **File the note** — save to `C:\Personal\Aethion\` following the vault's own CLAUDE.md router
   (ask the router where technique notes belong; don't invent structure). Title pattern:
   `DJ Technique — <topic> (<artist/channel>)`. Link related notes.

4. **Make it reproducible in dj-holo** (`C:\Dev\fullstack\dj-holo`) — translate the described
   transition into a recipe the user can perform, e.g.:
   - "sync B, kill B lows, 8-bar crossfade, swap lows at midpoint, release FX on drop"
   - map each step to app controls (keys/`M` automix/EQ sliders); automix bar-count lives in
     `src/control/automix.ts` (`autoMix(bars)`).
   - if a technique needs a missing engine feature (e.g. echo-out exit), note it in the repo's
     `docs/HANDOFF.md` extension table instead of hacking it in.

5. **Practice material** — if tracks are needed, fetch royalty-free equivalents with the
   `music-fetch` skill (NCS etc.) rather than the copyrighted originals.

## Reference points

- dj-holo docs: `docs/GESTURES.md` (controls), `docs/ARCHITECTURE.md` (what the engine can do).
- Mixes land in the in-app MIXES shelf; export finished ones to `C:\Personal\exports\mixes\`.
