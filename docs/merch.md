# Merch

Design notes for GPTilt apparel. First run: four T-shirts for **IEEE Conference
on Games, September 2026** (four conference days, one shirt each).

Brand rules live in [`brand.md`](brand.md). Nothing here overrides them.

## Standing decisions

### Fabric: black, all of it

The logo is white-and-cyan on near-black and has no light-background variant,
and `DESIGN.md` forbids inverting the Void BG. A white tee would mean redrawing
the mark. Black is also the one colour every print shop stocks, and it sits
within a few percent of Void BG `#050A1F`, so the logo's own dark background
disappears into the fabric instead of showing as a panel.

### Back of shirt: identical on all four

```text
        github.com/gptilt
     huggingface.co/gptilt
```

JetBrains Mono Medium, `#E2E8F0`, ~4in wide, centred between the shoulder
blades, 3-4in below the collar seam. Legible from ~3m — about the distance
someone reads your back across a poster session.

### QR code: yes — but the light variant only

Confirmed for the back, alongside the link block.

**Use `qr-huggingface-light.png`** (dark `#050A1F` modules on a light `#E2E8F0`
patch). Not the void/dark variants.

Reason, measured with OpenCV's `QRCodeDetector` against all three files:

| File | Modules on | Decodes as printed? |
| --- | --- | --- |
| `qr-huggingface-light.png` | `#050A1F` on `#E2E8F0` | **yes** |
| `qr-huggingface.png` | light on black | no — only after inversion |
| `qr-huggingface-void.png` | `#E2E8F0` on `#050A1F` | no — only after inversion |

The QR spec assumes dark modules on a light background. Inverted codes scan on
some modern phones and fail on others, which is not a gamble worth taking on a
garment you cannot re-print at the venue. Printing a light patch on the black
tee also reads as a deliberate HUD panel rather than a mistake.

All three encode `https://huggingface.co/gptilt` correctly. Geometry is
spec-compliant: 33 modules (version 4), 20px per module, 4-module quiet zone.

Print at **1.5-2in (4-5cm) square including the quiet zone** — that keeps the
module above 1mm and scans comfortably at arm's length. Never crop the quiet
zone.

Open point: this QR covers HuggingFace only; GitHub is text-only on the back.
Either accept that, or swap the target to `github.com/gptilt` as the org hub
that links onward to everything else. A matching GitHub QR can be generated in
the same style if two codes are wanted.

### Logo: vectorized ✅

`docs/logo.png` (612 x 535, opaque `#070E1A` background baked in) was not
printable — 2in at 300 DPI, and the background would have shown as a dark panel
on the fabric. Now traced to vector:

| Asset | Use |
| --- | --- |
| `logo.svg` | Primary. Full colour, transparent, brand-exact `#00E5FF` / `#FFFFFF`. |
| `logo-mono-white.svg` | One-colour print, embroidery, dark surfaces. |
| `logo-mono-black.svg` | Light surfaces, documents, print fallback. |
| `logo-print-3600.png` | 3600px raster, transparent, for printers that reject vector. |

Colours were snapped from the source's `#31E5FD` / `#070E1A` to the brand values
in `brand.md`. Trace fidelity against the source: white IoU 0.9999, cyan IoU
0.9846. Also fixes the favicon, which is still Astro's stock default.

## Print specs

- Front graphic: 10-11in wide, top edge ~3in below collar. DTG max is
  typically 12in x 16in — stay inside it.
- Export at **300 DPI**: a 12in print is 3,600 px.
- Vector (SVG/PDF) preferred over raster wherever the printer accepts it.
- Colours: `#00E5FF` cyan, `#FFCC00` gold, `#E2E8F0` text, on black.
- Neon cyan prints duller than it looks on screen — DTG on black lays a white
  underbase first. Expect some loss of glow; do not compensate by
  oversaturating, it prints muddy.

## The four shirts

### Day 1 — Identity

**Treatment:** logo-led, with words.

- **Front:** the vectorized logo, oversized (~11in), rotated slightly off-axis
  so it reads as *tilting*. Prompted hexcore energy treatment behind it.
- Wordmark **GPTilt** beneath, Rajdhani ExtraBold.
- Mono line beneath that: `[citation needed]`
- **Back:** shared link block + QR.

No tagline, no mission statement. `[citation needed]` does the work — it is an
academic in-joke that lands at this venue specifically, and it invites the
question rather than answering it.

### Day 2 — Smurfs

**Treatment:** text-only. The conference conversation starter.

- **Front:** `YET ANOTHER REASON TO DISLIKE SMURFS`
  Rajdhani ExtraBold, cyan `#00E5FF`, full width, three or four lines.
- **Back:** above the shared link block, JetBrains Mono:

  ```text
  smurfs →  training data bias
            evaluation bias
            data leakage

       WE NEED BETTER DATA
  ```

Front is the joke, back is the evidence and the thesis. The three failure modes
are verbatim from `gptilt/research`, `papers/smurfs.tex`.

### Day 3 — Open data

**Treatment:** typography, optional prompted background texture.

- **Front:** one number, standing alone, as large as the print area allows:

  ```text
  10,000,000
  events
  ```

  Rajdhani ExtraBold, tabular lining numerals (`brand.md` Number Styling —
  comma separators above 9,999). Beneath, in gold `#FFCC00`:
  `NO BLACK BOXES.`
- **Back:** shared link block + QR.

The number is real and shipped: `lol-ultimate-events-challenger-10m` on
HuggingFace. `No black boxes` is from the Open Intelligence trait in `brand.md`.

### Day 4 — Patch overfitting

**Treatment:** fully prompted hero graphic.

- **Front:** generated visualization of win-probability curves degrading across
  successive patches, with `DON'T INTERPRET THE GAME. MEASURE IT.` set beneath
  it as real type.
- **Back:** shared link block + QR.

From `papers/meta.tex`, *Towards Patch-Insensitive Models*. Tagline is the
research-facing alternative in `brand.md`.

## Prompts

Generate **graphics only**. Never let an image model render the URLs or
headlines — it will corrupt `huggingface.co/gptilt` into something unscannable.
All type is set afterwards in vector.

### Day 1 — energy treatment behind the logo

The mark itself is `logo.svg` composited on top. This generates only the
environment around it.

```text
Abstract energy field, flat vector, deep void navy #050A1F background.
Radiating cyan #00E5FF light shards and fine particle streaks emanating
outward from a single empty centre, sparse and asymmetric, thin sharp
geometric slivers of varying length, brightest near the centre and fading
to nothing at the edges. Large empty circular void in the middle.
No text, no letters, no symbols, no logo, no watermark.
High contrast, generous negative space, dark mode only, tactical
hextech aesthetic.
```

### Day 3 — background texture

Layer faintly behind the numerals at 15-20% opacity.

```text
Extremely subtle abstract topographic contour lines, deep navy #0F2549
on void black #050A1F, very low contrast, thin 1px strokes, evenly
distributed across the frame, no focal point, seamless texture,
flat vector, no text, no symbols.
```

### Day 4 — hero graphic

```text
Minimal scientific data visualization, wide 16:9, pure flat vector style.
Five thin glowing line-charts of win-probability curves, left to right,
each progressively more erratic and degraded than the last — the first
smooth and confident, the last noisy and scattered. Bright cyan #00E5FF
lines on a deep void navy #050A1F background, thin 2px strokes, subtle
outer glow only on the first curve. Faint 1px gridlines in #0F2549.
Single small gold #FFCC00 marker at the point of steepest degradation.
No text, no numbers, no labels, no axis titles, no watermark.
Sharp geometric precision, tactical HUD aesthetic, high contrast,
generous negative space, dark mode only.
```

## Open questions

- QR target: HuggingFace (current) or GitHub as the org hub? One code or two?
- Print shop not yet chosen — confirm max print area and whether they accept
  vector before final export.

## Disclaimer

Standard GPTilt disclaimer applies to anything public-facing: not endorsed by
Riot Games. Avoid champion art, Riot marks, and in-game assets on merch
entirely — none of the four designs above use any.
