## Deliverable

A single self-contained file **`public/showcase.html`** — pure HTML with inline CSS and JS, everything else via CDN. No build step. You'll open it at `/showcase.html` in the preview, and it's downloadable as one file.

**Concept:** *"AURORA — a creative art experiment"*. Not a product page, no marketing copy. Just an immersive interactive canvas that shows off maximum craft in the Aurora Obsidian palette (#0a0a1a → #141432, violet #7c3aed, cyan #22d3ee).

## Experience (single continuous scroll)

1. **Boot sequence** — brief black screen, scramble-loading counter (0→100), curtain wipes open
2. **Hero canvas** — full-viewport WebGL aurora shader (custom GLSL, mouse-reactive flow field), giant Instrument Serif word "AURORA" with per-char stagger + scramble effect, blended custom cursor
3. **Infinite marquee** — dual-direction ticker with mix-blend-mode text
4. **Interactive particle field** — Three.js 3000-point galaxy that repels from cursor, drag to rotate camera, scroll changes dispersion
5. **Pinned scroll-scrubbed sequence** — a rotating glass torus (Three.js) whose rotation, color, and paired poetry text are scrubbed by scroll position
6. **Bento gallery** — 6 asymmetric vanilla-tilt cards, each with a unique micro-canvas animation inside (noise waves, ASCII rain, orbiting lines, gradient mesh, ripple grid, wire-globe)
7. **Magnetic playground** — grid of Lucide icons that magnetically follow the cursor with spring physics
8. **Audio-reactive-style orb** — SVG orb with animated equalizer bars driven by pointer velocity
9. **Closing sigil + credits** — animated gradient border, footer with lib credits

## Libraries (all via CDN, zero install)

- **GSAP 3 + ScrollTrigger + Observer** — timelines, scroll-scrub, pin
- **SplitType** — per-char/word text splitting for reveals + scramble
- **Lenis** — inertial smooth scroll (respects prefers-reduced-motion)
- **Three.js (ESM)** — WebGL shader hero, particle galaxy, torus scene
- **Vanilla-tilt** — 3D card tilt with glare
- **Lucide** (CDN icons script) — modern iconography
- **Google Fonts:** *Instrument Serif* (display) + *Geist Mono* (accent) + *Geist* (UI) via `<link>`

## Design system (inline `<style>`)

- Deep obsidian base, violet↔cyan aurora gradients, glass surfaces with SVG noise data-URI
- Fluid `clamp()` type, 8px grid, generous whitespace
- Blended custom cursor (`mix-blend-mode: difference`) with hover growth on interactive elements
- Respects `prefers-reduced-motion` — disables scroll-scrub, particle loop, and cursor blend

## Technical guarantees

- One file, ~1 file to download
- Handles resize, pointer, touch (no cursor blend on touch)
- Cleans up rAF loops on unload
- Responsive down to 360px
- No frameworks, no bundler — opens standalone in any modern browser

## File changes

- **Add** `public/showcase.html` — the full experience

That's it — the TanStack app is left untouched. Preview at `/showcase.html`.
