# Anjuna MIDI Generator (Ableton Live 10 Suite)

A single offline `index.html` (vanilla JS + CSS, no dependencies, no build step) that generates original,
genre-correct MIDI parts (chords, harmony, bass, kick, drums, pattern, arpeggio, lead) in the deep house / melodic house / progressive house / progressive trance /
uplifting trance space, shows a Live 10 sound-design card for every part, and exports `.mid` files.

## Use

1. Double-click `index.html` (Chrome, Edge or Firefox). No internet needed.
2. Pick a genre or an artist-style preset, key, scale and bar count. BPM follows the genre and stays editable.
3. Press **Generate all**, or click a card in the **Preset library**. The same seed always gives the same
   result; **Re-roll** picks a new seed; **Regenerate** on a part changes only that part
   (regenerating Chords also re-fits every melodic part to the new progression; the "Thirds below the lead" harmony style follows the Lead part).
4. Shape it with Swing, Complexity, Energy, Humanize and each part's **Style** menu.
5. **Play preview** / **Play all** audition with a simple built-in synth.
6. **Download .mid** per part, **Export all parts (separate .mid)**, or **Export combined multitrack .mid (Type 1)**.

## Import into Ableton Live 10

1. Set Live's tempo to the BPM shown in the tool (Live ignores tempo stored in dragged MIDI files).
2. Drag a `.mid` from your download folder onto a MIDI track (Session slot or Arrangement).
   Drop the combined Type 1 file on the empty drop area to get one track per part.
3. **Kick / Drums:** load a Drum Rack. Notes use the GM layout from C1: 36 kick, 37 rim, 38 snare, 39 clap,
   41/43/45 toms, 42 closed hat, 46 open hat, 51 ride, 70 shaker.
4. **Chords / Harmony / Bass / Pattern / Arpeggio / Lead:** load the instrument named on the sound-design card (Wavetable, Operator, Analog)
   and dial in the listed values. Put a Compressor with sidechain from the kick on each of them.
5. Clips are exactly the chosen number of bars and loop cleanly.

## Self-test

Open the browser console and run `runTests()`. It checks scale membership, pitch ranges, loop length,
MIDI header/track validity (round-trip parse), same-pitch overlaps, determinism, kick quantization and BPM ranges.

## Customising

- Artist-style presets are editable JSON in the page ("Artist-style presets"), saved in `localStorage`.
- All UI and sound-card text lives in the `STR` object at the top of the script for translation.
