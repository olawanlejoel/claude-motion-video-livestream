# Motion Video Style Guide

A reusable direction for animated product/brand videos, built from the Zofu motion pieces: the launch film, "7.4 Seconds", "One Take" (how-it-works) and its voiceover version. It covers **how they look, move and sound**, not what they say, so it works for any product, script or story.

Hand it over with a website, brand file or script: *"Make a motion video using the Motion Video Style Guide."*

---

## 1. The style in one line

**The brand's real UI, rebuilt and animated on a musical beat grid: kinetic type rising through masks, cinematic transitions, a cursor that does the work, and a soundtrack where every cut, pop and click is locked to the music.** It should feel like a Silicon Valley launch film: confident, clean and fast, with nothing on screen that doesn't move with purpose.

---

## 2. Format & export

| Setting | Value |
|---|---|
| Landscape (default) | 1920 × 1080, **60 fps** |
| Vertical variant | 1080 × 1920 (re-layout, don't just crop) |
| Length | 30 s (ads, explainers) · 40–60 s (launch films) |
| Video | H.264, yuv420p; master at CRF 14–17, then a two-pass delivery copy at ~3.3 Mbps if a size cap applies (e.g. < 30 MB) |
| Audio | AAC 192–256 kbps, 48 kHz, **−14 LUFS**, true peak −1 dB |

---

## 3. Concept archetypes (pick one per video)

Every video needs **one idea**, not a feature list. These five worked:

| Archetype | How it works | Zofu example | Best for |
|---|---|---|---|
| **Launch film** | Hook → social proof burst → meet the product → features → how it works → teaser → CTA | Launch film v2 (62 s) | Launches, homepages |
| **Race against the clock** | A real stat becomes a countdown. Fail once, rewind, succeed with the product | "7.4 Seconds" (30 s) | Problem/solution ads with a hard number |
| **One take** | A single continuous shot of the app; a cursor does every step on the beat; a big counter tracks progress | "One Take" (30–40 s) | How-it-works, onboarding, tutorials |
| **Testimonial burst** | Real quote cards pop on every 8th note, scatter, and reveal a headline | Launch film section 2 | Social proof |
| **Teaser** | Dark stage, glowing oversized type, shimmer sweep, music breakdown and build | "V2 coming soon" | Upcoming features, waitlists |

**Rules for any concept**
- **Hook in the first 2–3 s:** a question, a stat, or the brand reveal on a hit.
- **One clear CTA at the end:** the URL in a pill, held for at least 2 s.
- **Use only real content:** the actual site, real testimonials, real stats with sources. Label illustrative numbers ("Illustrative example").

---

## 4. Visual system

**Build from the brand's own assets.**
- **Website SVG/Figma export:** render it at 2× with backgrounds stripped so cards come out as transparent cutouts; render individual groups by bounding box.
- **Bitmap logo:** vectorise it (trace at 8×, drop the outer frame contour) so it stays sharp full-screen; split the mark and the wordmark so they can animate separately.
- **Live text:** recreate key components as HTML (score rings, toggles, chips, forms, before/after cards) so numbers count, rings fill, toggles flip and text types.
- **Real screenshots** (e.g. the sign-up page): use them where possible and match the copy exactly.

**Typography**
- Headlines in a tight grotesk (**Inter Tight 500, −0.055em tracking, line-height 1.0**).
- Two-tone headlines: line one in primary, line two in a muted or accent colour ("Your next chapter. / *Starts with you.*").
- Eyebrows: 16–20 px, uppercase, +0.2em tracking.
- Serif italic (**Instrument Serif**) for single expressive words ("*not hours.*").

**Colour (default: Zofu; swap per brand)**
- Forest `#123E33` and ink `#162D2A` for dark stages.
- Lime `#D0FA79` as the single loud accent.
- Cream `#FDFDF9` and sage `#F1F3ED` for light stages.
- Feature panels in lilac `#E2D0F6`, lime `#D4EF8D`, yellow `#FFCF5C`, sky `#CFE6F7`, peach `#F3B7A3`.
- Danger red `#E0563B`.
- Photo backgrounds (e.g. the sky) with a soft blue gradient overlay for text contrast.

**Stage recipes**
- **Dark stage:** radial glow, `radial-gradient(ellipse at 50%, #1E5A45 0%, #123E33 55%, #0B2820 100%)`, plus optional drifting accent particles.
- **Light stage:** cream with a faint 60 px grid masked to the centre and a soft lime glow.
- **Brand sky:** the hero photo, scaled 1.08–1.45 with a slow parallax.

---

## 5. Motion language

**Easing (the whole feel lives here)**

| Use | Curve |
|---|---|
| Entrances | **easeOutExpo** `1 − 2^(−10k)` |
| Pops and stamps | **easeOutBack** (overshoot 1.6–2.4) |
| Panel moves and wipes | **easeInOutExpo** |
| Counters, rings, line draws | **easeInOutCubic** |
| Exits | **easeInExpo** |

Never linear, except for progress bars and typing.

**Kinetic type**
- Each word sits in an overflow-hidden mask and **rises 135% → 0** with a 6° → 0° rotation.
- Stagger: **0.07–0.09 s per word**, duration 0.8–1.0 s.
- Exit: words lift out −150% with a 0.035 s stagger.
- Hide fully masked words with `visibility` so no descender slivers show.
- Small type (eyebrows, body) fades and rises 20–24 px instead.

**Card and UI entrances**
- Fly in with perspective (1400–1600 px).
- Start offset 400–700 px, rotateX/Y 20–35°, blur 10–14 px, scale 0.6.
- Settle with expo; stagger cards 0.15–0.35 s.
- Then **keep everything alive:** float (sine, ±4–8 px, 1.2–1.7 Hz), slow parallax drift, gentle camera push (scale 1.00 → 1.05).

**Numbers and UI states**
- Counters ease up (e.g. 41 → 94) while the ring fills.
- Ring colour shifts red → amber → lime as the value rises.
- Toggles flip with a knob slide and colour swap.
- Typing runs at a steady rate with a blinking caret (4 Hz).
- Strikethrough draws left to right before the rewrite types in.

**The cursor (for walkthroughs)**
- A real arrow cursor moves between targets on **easeInOutCubic**.
- Targets are read from live element positions.
- Each click is a 0.82× press plus an expanding ring ripple (0.45 s).
- Fields light up with an accent glow while focused.
- Drag-and-drop: the file follows the cursor with a slight tilt; the drop zone glows on hover.

---

## 6. Transitions catalogue

| Transition | How | When |
|---|---|---|
| **Burst iris** | The brand starburst grows ×20 (easeInExpo), filling the screen with accent colour; a circular clip-path iris then opens the next scene from the centre | Into the hero; section openers |
| **Zoom-through** | The camera scales into a card ×5 with blur, plus a white flash at 60% | Out of a dense UI moment |
| **Panel swipe** | Full-screen colour panels slide in from the right (expo, 0.75 s); the previous panel pushes 420 px left and dims | Feature-by-feature runs |
| **Curtain rise** | The next scene rises from the bottom via clip-path inset with rounded top corners (80 px → 0) | Mood shifts (light → dark) |
| **Push up** | The current scene slides up 1080 px while the next follows | Section to section |
| **Scanline wipe** | An accent line with glow sweeps down, revealing the "after" state beneath | Before → after transformations |
| **Tape rewind** | Jitter, RGB split, scanlines, "◀◀ REWIND" badge, timer counts back up | "Let's try that again" beats |
| **Hard cut on the hit** | Cut exactly on a beat, with a full-screen accent flash fading over 0.45 s | Logo reveals, drops |
| **Scatter** | Cards fly outward from centre with rotation and blur, staggered | Clearing a busy collage |
| **Strip slide** | Inside an app window, screens slide horizontally with motion blur | One-take step changes |

Always place transitions on the beat grid (section 7).

---

## 7. Timing & the beat grid

- Default tempo is **120 BPM** (beat = 0.5 s, bar = 2 s).
- **Scene changes land on bar lines; pops and stamps land on beats or 8th notes.**
- Bursts of items (cards, chips, tiles) pop every **0.25 s (8th notes)**, each with a pitched pop rising up a pentatonic scale.
- Give each scene's key message **at least 1.5–2 s of readable hold** after its entrance finishes.

---

## 8. Sound design

The soundtrack is composed for the edit, not dropped on top. Every visual event has a sound.

**Music** (synthesised; original and licence-free)
- Key and chords: F major, Fmaj9 → Am7 → Dm9 → B♭maj9, one chord per bar.
- **Pad:** detuned saws, low-passed (900–1100 Hz in intros/breakdowns, ~2600 Hz in the groove).
- **Arpeggio:** a 16th-note pluck, an octave up in the second half of each bar once the groove is full.
- **Drums and bass:** kick on every beat with 65% sidechain pumping on the music; off-beat hats plus 16th ghost hats; claps on beats 2 and 4; 8th-note sub bass with an octave bounce.
- **Structure:** intro (filtered, no drums) → **drop on the hero reveal** → groove → **breakdown** for a mood shift or teaser (no kick, snare roll building over the last 1.75 s) → final drop → resolving chord under the end card.

**SFX mapping**

| Visual event | Sound |
|---|---|
| Panel or camera move | Filtered-noise whoosh, panned in the direction of motion |
| Big reveal or scene drop | Sub impact plus noise burst, with a chime chord |
| Build-up | Riser (rising noise and tone) over 1–1.4 s |
| Card or chip pop | Pitched pop, plus a soft pluck on the same note |
| Counter or score | Rapid clicks, accelerating and rising in pitch, ending on a chime |
| Typing | Keyboard ticks (randomised pitch and timing) |
| Click | Short mouse click |
| Drag and drop | Pickup pop, then a soft thud on drop |
| Success | Two-note chime / notification ding |
| Failure stamp | Impact plus low buzzer |
| Rewind | Tape warble sweeping up, ticks reversing |
| Countdown | Clock ticks every 0.25 s, with a heartbeat underneath |

**Mix**
- Light reverb on music and SFX; a short room on drums.
- Soft-clip glue, then normalise to **−14 LUFS**.
- When a voiceover is present, duck music and SFX about 8 dB under the voice.

---

## 9. Voiceover (optional)

- **Engine:** Kokoro (open source). Good default voices: `af_heart` (female, US) and `am_michael` (male, US). Generate both and let the client pick.
- **Script:** one line per scene, starting about 0.25 s after the scene lands. Full sentences are fine if the timing allows.
- **Fit check:** time every generated line against its scene window. If a line runs long, **stretch the video**, don't rush the voice: insert slow-motion holds (playback at 10% speed) after each step's action completes. Actions stay at full speed while the scene "breathes" for the line.
- **Pronunciation:** check how brand names come out and respell them phonetically (e.g. "Zohfoo" for Zofu).
- **Voice chain:** high-pass 90 Hz, presence boost (2.5–6 kHz), light compression, then ducking under the music.

---

## 10. Production pipeline

1. **Extract:** render the site or design at 2×, cut out components, vectorise the logo, and read all copy, colours and fonts.
2. **Storyboard:** write a scene list with start times on the bar grid, plus an event list (every pop, click and cut with a timestamp).
3. **Build:** one HTML page with a pure `render(t)` function that sets every element's state from the time alone (deterministic, seekable). Each scene is a function of local time; reuse scenes by offsetting time.
4. **Preview:** render stills at key times into a contact sheet. Check overlaps, clipping, legibility and empty frames before any full render.
5. **Render:** headless browser frames at 60 fps, piped to ffmpeg, split across workers in parallel; then concatenate.
6. **Score:** generate music and SFX from the same event list, so the audio lines up with the picture to the frame.
7. **Mix and deliver:** mux, normalise loudness, spot-check frames from the final file, and make a size-capped copy if needed.

---

## 11. Pitfalls we hit

1. **Masked words leave slivers.** Push hidden words to ±135–150% and set `visibility: hidden` when fully out.
2. **Logo from a PNG is blurry at full size.** Vectorise it; a trace may include the background frame, so drop the contour that spans the full image.
3. **Local `fetch()` fails** in headless renders of `file://` pages. Inline assets (SVG paths) into the HTML instead.
4. **Text collisions.** Two-line titles in fixed-height slots spill into the next one. Size slots for the longest title and check stills.
5. **Name clashes in render scripts** (e.g. a worker-count variable shadowing the time-warp function) can hang a parallel render waiting on a pipe. Use distinct names and watch the logs.
6. **Upload limits.** Long 60 fps masters are big; always make a two-pass delivery copy.
7. **Unverifiable claims.** Source any stat on screen. Keep illustrative scores and example users clearly fictional, and say so.

---

## 12. Checklist

- [ ] One concept chosen; hook in the first 2–3 s; single CTA with URL
- [ ] Brand assets extracted; logo vectorised; real copy and screens used
- [ ] Scene list on the 120 BPM bar grid; event list written
- [ ] Kinetic type with mask rise and stagger; two-tone headlines
- [ ] Every element eases (expo / back / cubic); nothing static; floats and parallax on
- [ ] Transitions chosen from the catalogue, landing on bar lines
- [ ] Contact-sheet review: no overlaps, clipping or unreadable text
- [ ] Music arranged (intro → drop → groove → breakdown → drop → resolve)
- [ ] An SFX for every visual event; −14 LUFS
- [ ] Optional VO: lines fit, brand pronunciation checked, music ducked
- [ ] Stats sourced on screen; illustrative content labelled
- [ ] Master plus size-capped delivery copy; final file spot-checked
