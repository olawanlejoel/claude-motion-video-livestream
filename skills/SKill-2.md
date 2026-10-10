---
name: motion-video
description: Make motion-graphics videos rendered from code (launch films, product reels, showreels, explainers, kinetic type, social ads, logo bumpers, animated stories). Use whenever someone asks to make a video, animate something, or create a reel, promo or explainer, even if they don't name any tools.
---

# Motion Video

You're already a strong motion designer. This skill only adds the few things that
separate a great video from a generic one. Keep it fast: build, look once, fix, ship.

## Before you build (one short pass, don't over-plan)
- **One idea, exact words.** Write the on-screen text as a short numbered list:
  hook in the first 2 s → the point → CTA held at least 2 s. If the user gave the words,
  use them exactly.
- **Use real stuff.** The user's logo, colours, fonts, screenshots and copy. Never invent
  product UI, stats or quotes.
- **Pick a look.** If there's a reference, copy its pacing, type and transitions, never
  its content. If not, choose one display font, one accent colour and one clear style,
  and commit to it.

## How it's built
- One HTML file with `window.seek(t)` that draws the exact frame for time t. No timers,
  no CSS transitions, no `Math.random` (use a seeded random). Render frames with headless
  Chrome (Playwright) and encode with ffmpeg: H.264, yuv420p, 60 fps.
- Don't pull in a video framework unless the user asks for one.

## Motion that feels expensive
- Springs or ease-out curves, never linear. Stagger items 0.06–0.09 s apart; never move
  everything at once.
- Big moves get a small anticipation before and a settle after. Heavy things move slower.
- Show one idea at a time. Let text land, then hold it long enough to read
  (about 0.33 s per word).
- Something new every 2–4 s, with uneven shot lengths.

## Never
Centered title on a gradient, everything fading in, text or labels in the corners,
glows, particle bursts, robot/brain/sparkle clichés, dead seconds where nothing happens.

## Sound
Put cuts on a beat grid (120 BPM: a cut every 2 s bar, pops every 0.5 s beat).
Synthesize music and SFX in code from the same timings, or snap cuts to the supplied
track. Every big moment gets a sound. Master to about −14 LUFS.

## Look once before the final render
Render one still every 0.5 s as a contact sheet and actually look at it. Fix the worst
problems: overlapping or unreadable text, dead beats, the banned looks. Then render the
full video and deliver the MP4.