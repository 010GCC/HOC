# Horizontal Office Chair (HOC)

A single-file browser endless runner: lean back in your office chair, roll through a neon office, and dodge pink workplace hazards.

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

On touch devices, on-screen buttons appear during play:

- **JUMP** / **DUCK** — right side
- **FWD** / **BWD** — left side (move the chair)
- **TRICK** — left side (lights up when a trick window is open)

Landscape is recommended; portrait is supported. The game fills the full viewport on phones and tablets (safe-area aware). Use **Play anyway** if the rotate prompt appears.

## Files

| File | Purpose |
|------|---------|
| `index.html` | Entire game (HTML / CSS / canvas / audio / leaderboard) |
| `favicon.ico` | Site icon |
| `CNAME` | Custom domain for GitHub Pages (`hochairz.cc`) |
| `NEXT_STEPS.md` | Optional notes for leaderboard setup |
| `HOC Game Build Document.docx` | Design / build notes |

## Deploy (GitHub Pages + custom domain)

This repo is set up for **GitHub Pages** from the `main` branch root.

1. In the repo **Settings → Pages**, set source to **Deploy from a branch**, branch `main`, folder `/ (root)`.
2. `CNAME` already points to **`hochairz.cc`**. Point your DNS:
   - Apex / `www` (or your host records) to GitHub Pages as required by [GitHub’s custom domain docs](https://docs.github.com/en/pages/configuring-a-custom-domain-for-github-pages).
3. After DNS propagates, https://hochairz.cc should serve `index.html`.
4. Fallback URL: https://010GCC.github.io/HOC

No build step — edit `index.html` and push.

## Leaderboard

Scores use Firebase Firestore when configured in `index.html`. Offline / failed submits fall back to a local cache. See `NEXT_STEPS.md` for related setup notes.

## Local preview

Open `index.html` in a modern browser, or serve the folder:

```bash
npx --yes serve .
```

Then visit the printed local URL on desktop or your phone (same Wi‑Fi).

## License

All rights reserved unless otherwise noted by the repository owner.
