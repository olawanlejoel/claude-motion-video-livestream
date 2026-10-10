# Making Beautiful Animations with Claude, Figma & Agent Skills

Assets from the livestream where I explored how to turn designs into motion graphics with Claude, Figma and agent skills. I went live with Meeday, a design engineer, and we built animations on stream, including what worked and what didn't.

**Watch the stream:** [Making Beautiful Animations with Claude, Figma & Agent Skills | Live](https://www.youtube.com/live/mPg5AcJYmOc) on Code With Joel

## What's in this repo

```
prompts/   The prompts used on stream
videos/    The videos rendered from them
skills/    The agent skill and style guide that drive the video output
links.md   Tools and inspiration mentioned during the stream
```

### Prompts

| File | What it makes |
|---|---|
| `prompt-1` | A video of Spidra scraping Indeed |
| `prompt-2`, `prompt-3` | A 10-second cinematic launch video |
| `prompt-4` | A 30-second cinematic launch video |
| `project-6-tesla-ev` | A 10-second EV launch ad for a fictional Tesla Nigeria launch |
| `prompt-5-know-maggi` | A 20-second vertical (9:16) Knorr food ad, "The Flavour Switch" |

Prompts 1 to 4 expect a markdown file attached that describes the product's colours and UI. The Tesla and Knorr prompts are self-contained, though the Knorr one works best with your own product photos.

### Skills

| File | What it is |
|---|---|
| `skills/SKill-2.md` | The `motion-video` agent skill: a short set of rules for making motion-graphics videos from code |
| `skills/SKILL-1.md` | A longer motion video style guide covering look, motion, transitions and sound design |

To use the skill with Claude Code, put `SKill-2.md` in a folder under `.claude/skills/` (for example `.claude/skills/motion-video/`) and name it `SKILL.md`. Attach the style guide to your prompt when you want a specific look.

## How the workflow fits together

1. Get the real UI or assets into Figma (the [Figma Chrome extension](https://www.figma.com/downloads/chrome-extension/) captures a live page as editable layers) and export SVGs.
2. Give Claude the agent skill, a style guide and a prompt from `prompts/`.
3. Claude builds the animation and sound from code and renders the video.
4. Look at the result, then adjust the prompt and render again.

## Notes

- The Tesla and Knorr ads are unofficial concepts made for demonstration. Both brands belong to their owners.

## Links

Tools and inspiration are listed in [links.md](links.md). Stream announcements:
[LinkedIn post](https://www.linkedin.com/feed/update/urn:li:activity:7514641229117046785/) · [LinkedIn event](https://www.linkedin.com/events/makingbeautifulanimationswithcl7514641225585713153/)

## About

Made by Joel Olawanle, who builds Spidra and NGN Market. Livestreamed on the Code With Joel YouTube channel.
