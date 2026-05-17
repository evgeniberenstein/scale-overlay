# Scale Overlay

A mobile-first interactive guitar scale visualizer that lets you overlay multiple scales simultaneously on a single fretboard — built for improvisation study, music theory exploration, and ear training.

**Live app:** `https://evgeniberenstein.github.io/guitar-scale-trainer/scale-overlay.html`

---

## Features

### Multi-Scale Fretboard
- Overlay up to **4 scales simultaneously** on a single fretboard
- Each scale gets its own **auto-assigned color** (swappable)
- Notes shared by all active scales get a **white ring** highlight
- Notes in only one scale are **dimmed** to reduce visual noise
- **Pie-segment dots** when a note belongs to multiple scales
- **Root notes** marked with a color ring per scale

### Scale Selection
- **Drag-and-drop slots** to reorder scales
- **12 curated scales**: Major, Natural Minor, Harmonic Minor, Melodic Minor, Major Pentatonic, Minor Pentatonic, Blues, Dorian, Phrygian, Lydian, Mixolydian, Locrian
- Each scale has an **independent root** (e.g. A Dorian + C Major simultaneously)
- Per-slot **on/off toggle** to hide/show a scale without removing it

### Fretboard Navigation
- **5-fret draggable window** — drag left/right or use ‹ › buttons
- Full 22-fret neck, window slides smoothly
- **4 dot label modes**: Note names / Scale degrees / Root·3rd·5th only / Color only

### Chord Popup
- Tap **♩ Chords** on any slot to open a position-aware chord diagram popup
- Shows all **diatonic chords** with Roman numeral analysis (I ii iii IV V vi vii°)
- **SVG fingering diagrams** built from the CAGED voicing engine — positions shift automatically to match the current fret window
- Works correctly for all scale types including blues and pentatonics

### Note Tooltip
- **Tap any dot** on the fretboard to see which scales contain that note
- Shows the **scale degree** (1, b3, 5…) in each scale's color
- **Tap again** to dismiss (toggle behaviour)

### Analysis Panel
- **Common notes** listed as tags (notes shared by all active scales)
- **Pairwise relationship text**: subset detection, shared note count, unique additions
- **Automatic modal detection**: e.g. "D Dorian = mode 2 of C Major"

### Presets
- 6 **built-in presets**: Min Pent + Dorian, Major + Maj Pent, Pentatonics, Minor Modes, Blues Box, All 4
- **Save your own** named presets to browser memory
- All state **persists across sessions** via localStorage

### Audio
- **▶ Play** button on each slot arpeggios the scale via Web Audio API
- Notes flash on the fretboard in sequence as they play

### Optional Panels
- **♩ Chord voicings** toggle — diatonic chord diagrams per active scale
- **◎ Practice tracking** toggle — rep counter per scale slot

### Color System
- **6 color palettes**: Vivid, Pastel, Neon, Earthy, Ocean, Sunset
- **Custom hex input** for any color
- Palette switcher inside the color picker modal

### Hebrew / English
- Full **Hebrew UI** with one tap (EN/HE toggle button)
- RTL layout, translated scale names, chord qualities, analysis text
- **Solfège note names** in Hebrew mode: C=דו, D=רה, E=מי, F=פה, G=סול, A=לה, B=סי (with # accidentals)

### Theme
- **Dark / Light** theme toggle (◐ button)
- Dark: wood-textured fretboard, dark analytical panels
- Light: clean analytical style throughout

---

## Usage

No installation required. Open `scale-overlay.html` in any modern browser.

1. **Add scales** — tap an empty slot or change the root/scale dropdowns
2. **Drag to reorder** slots (long-press on mobile)
3. **Drag the fretboard** left/right to move the position window
4. **Tap any dot** to see note info
5. **Tap ♩ Chords** to see fingering diagrams for a scale's diatonic chords
6. **Toggle EN/HE** for Hebrew mode

---

## Scale Reference

| Key | Scale |
|-----|-------|
| `major` | Major (Ionian) |
| `minor` | Natural Minor (Aeolian) |
| `harm_minor` | Harmonic Minor |
| `mel_minor` | Melodic Minor |
| `maj_pent` | Major Pentatonic |
| `min_pent` | Minor Pentatonic |
| `blues` | Blues (6-note) |
| `dorian` | Dorian |
| `phrygian` | Phrygian |
| `lydian` | Lydian |
| `mixolydian` | Mixolydian |
| `locrian` | Locrian |

---

## Technical Notes

- **Single HTML file** — no build step, no dependencies, no server
- **Web Audio API** for scale arpeggio playback
- **SVG fretboard** rendered entirely in JavaScript
- **CAGED voicing engine** — chord voicings computed from interval theory, placed in the nearest position zone to the current fret window
- **localStorage** for state persistence (slots, colors, presets, theme, language)
- Tested on **iOS Safari**, Chrome, Firefox

---

## Credits

- Chord voicing shapes: CAGED system (public domain music theory)
- Fonts: [Space Mono](https://fonts.google.com/specimen/Space+Mono) + [Syne](https://fonts.google.com/specimen/Syne) (Google Fonts, OFL)
- Part of the [guitar-scale-trainer](https://github.com/evgeniberenstein/guitar-scale-trainer) project

## License

MIT — free to use, modify, and share.
