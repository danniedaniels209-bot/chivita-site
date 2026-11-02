# Chivita — Bright by Nature (concept site)

Run with a local server (the loader uses fetch, so file:// won't work):
`python -m http.server 8080` (Windows: `py -m http.server 8080`) → http://localhost:8080/

Everything lives in `index.html` (HTML, CSS and JS inline) plus `assets/`.

## Loading
1. The hero video downloads first behind the loader (progress shown). After 15s a "Continue without animation" option appears.
2. As soon as the page opens, every other asset downloads in the background (2 at a time):
   fruit video, pour video, all four flavour scenes and the breakfast image. A thin orange bar at the top shows progress and fades when done.
3. If you scroll to a section before its file has finished, that file jumps to the front of the queue.

## Animations
Each video (hero, closer look, first pour) restarts from the beginning every time its section comes into view, and pauses when it leaves. Text fades in on each visit (no bounce or water effects). No replay/play buttons. Reduced-motion users see the final frame.

## Headline animations
Headlines are inline SVG split into individual letters (the Canva artwork, unchanged in shape). Each replays every time its section comes into view:
- 01 Hero & 03 Pour: letters rise out of each line's baseline; the orange full stop drops in and sends out a ripple.
- 02 Closer look: focus pull — letters start big and blurred and snap sharp; the dot zooms in like a lens; the caption rule draws across.
- 04 Flavours: letters fill up from the base in the current flavour colour, then settle to green; the dot takes the flavour colour.
- 05 Breakfast: sunrise — warm orange letters drift up and cool to green; the dot rises last with a glow.
Hover (mouse only): letters lift in a wave around the cursor and turn orange (flavour colour in section 04); buttons get a light sheen and the arrow slides out and back; flavour arrows nudge; benefit icons spin.
Hero and pour videos play at 2x (data-speed="2" on the <video> tag; change the number to adjust).

## Flavours
Section 04 has large arrow buttons on either side of the product, a "1 / 4 · Tap the arrows to switch flavour" label and dots underneath. Keyboard ← → and swiping on the image also switch. Hero flavour tabs jump to section 04 with that flavour selected.

## Phones
There is no separate mobile layout. On a phone held upright the desktop layout is shown turned 90°, so visitors rotate the phone to view it. In landscape (or with auto-rotate) it shows normally. All sizes scale with the layout width.

## Assets
- Videos: original frames untouched (stream copy); audio track removed and faststart enabled.
- Scene images: WebP at quality 90 (≈0.6 MB total, was ≈9 MB PNG).
- `_source/` is not used by the site: animation frames, Google Flow prompt, Canva renders and unused images.

Independent design concept. Product imagery is illustrative.
