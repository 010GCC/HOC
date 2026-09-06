# Horizontal Office Chair (HOC)

A browser endless runner: lean back in your office chair, roll through a neon office, and dodge pink workplace hazards.

**Play:** [https://hochairz.cc](https://hochairz.cc) · [GitHub Pages](https://010GCC.github.io/HOC)

## How to play

Survive as long as you can. Obstacles scroll toward you; jump, duck, dash, and move the chair to avoid them. Land tricks during the **TRICK READY** window, chain near-misses, and climb through 67 levels.

### Desktop controls

| Action | Keys |
|--------|------|
| Jump / double jump | `Space` · `W` · `↑` |
| Duck | `S` · `↓` |
| Dash (brief invincibility) | `Shift` |
| Trick | `T` |
| Move chair | `←` `→` · `A` `D` |

### Mobile / touch

**Landscape only on mobile — hard lock.** Portrait on touch devices shows a rotate overlay that blocks play. There is no “Play anyway” path. **PLAY** / **PLAY AGAIN** / `startGame` refuse to start while portrait; the overlay is never dismissed in portrait. If you rotate to portrait mid-run, the overlay returns, input freezes, and the game loop pauses until you return to landscape. Disable rotation lock and turn the phone sideways.

On touch devices, on-screen buttons appear during play:

- **JUMP** / **DUCK** — right side
- **FWD** / **BWD** — left side (move the chair)
- **TRICK** — left side (lights up when a trick window is open)

The game stage keeps a **16:9** aspect ratio, fitted to the viewport, then scaled to **99%** and centered so browser chrome / edges do not clip the frame. Touch controls respect safe-area insets without shrinking the game frame via body padding.

Desktop (fine pointer, ≥900px) uses the same centered 16:9 frame with the 1% inset.

### Fullscreen + Add to Home Screen

- **Fullscreen API** — Tapping **PLAY** (or the in-game **FULLSCREEN** control, when available) requests fullscreen on the game container / document after that user gesture (standard + `webkit` prefixes). Exit via the control or the browser’s exit gesture. If fullscreen is unsupported or denied (common on **iOS Safari**), play still starts — fullscreen never blocks the game.
- **Fullscreen settle** — Entering/exiting fullscreen (and shortly after PLAY requests FS) runs multiple layout passes (`requestAnimationFrame` ×2 plus delayed timeouts ~50–350ms) that re-measure the stage (preferring the fullscreen element / `visualViewport` when needed) and re-init background layers in-game. CSS sizes `:fullscreen` / `#gameContainer:fullscreen` from the FS box (`100%` → 99% 16:9 centered) so letterboxing does not stay uneven until a manual resize/screenshot.
- **PWA / Add to Home Screen** — `manifest.webmanifest` uses `display: "standalone"`, theme/background `#0a0a0a`, name **Horizontal Office Chair** / short name **HOC**. Apple web-app meta tags are set for home-screen launch. When the Fullscreen API is unavailable (typical iPhone in-browser), a short dismissible hint explains **Share → Add to Home Screen** for chrome-free play; it stays below the portrait rotate overlay and does not appear in portrait.

## Files

| File | Purpose |
|------|---------|
| `index.html` | Bootloader that applies mobile landscape / viewport / fullscreen / PWA patches to the pinned game build |
| `manifest.webmanifest` | Web app manifest (`standalone`, theme `#0a0a0a`) |
| `icon.svg` / `icon-maskable.svg` | PWA / home-screen icons |
| `favicon.ico` | Site icon |
| `CNAME` | Custom domain for GitHub Pages (`hochairz.cc`) |
| `NEXT_STEPS.md` | Optional notes for leaderboard setup |
| `HOC Game Build Document.docx` | Design / build notes |

## Deploy (GitHub Pages + custom domain)

1. **Settings → Pages**: deploy from branch `main`, folder `/ (root)`.
2. `CNAME` points to **`hochairz.cc`** — configure DNS per [GitHub custom domain docs](https://docs.github.com/en/pages/configuring-a-custom-domain-for-github-pages).
3. Live: https://hochairz.cc · fallback https://010GCC.github.io/HOC

## Leaderboard

Scores use Firebase Firestore when configured. Offline / failed submits fall back to a local cache. See `NEXT_STEPS.md`.

## Local preview

Serve the folder (required so the bootloader can fetch the game source):

```bash
npx --yes serve .
```

## License

All rights reserved unless otherwise noted by the repository owner.
