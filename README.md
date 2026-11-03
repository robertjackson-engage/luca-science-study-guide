# Luca's Physics Lab

Motion and Forces study game for Luca: inertia, weight, equilibrium and force diagrams, speed/velocity/acceleration, free fall, Newton's laws, and dimensional analysis. Open `index.html` or visit the Pages URL.

Six labs map to the sections of the study guide (vocab, mass & weight, force diagram builder, speed lab, 3D drop lab, unit chains) plus a Boss Test that generates a fresh mostly-multiple-choice practice test with new numbers every time. Every answer has a sound and spoken feedback.

## Updating

Edit `index.html`, then:

```bash
git commit -am "update" && git push
```

## Audio

Voice clips and sound effects in `audio/` were pre-generated with ElevenLabs by `tools/gen_audio.py`, so the published site is fully static and contains no API key. To regenerate (existing files are skipped):

1. Put `ELEVENLABS_API_KEY=...` in a local `.env` file (it is gitignored).
2. In the browser console on `index.html`, run `copy(JSON.stringify(AUDIO_TEXTS()))` and save it to `texts.json`.
3. Run:

```bash
set -a && source .env && set +a && python3 tools/gen_audio.py texts.json
```
