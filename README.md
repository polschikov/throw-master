# Sport Masters

Public GitHub Pages release for the **Sport Masters** pixel-art athletics platform.

## Deploy

Upload the entire contents of this folder to a repository root with GitHub Pages
enabled. The loader and hub discover each other through `manifest.json`.

```text
index.html                          root loader (fetches manifest.json, opens hub iframe)
hub.html                            hub fallback
hub-<buildId>.html                  cache-busted hub
manifest.json                       main manifest: hub + games
games/<game-id>/game.html           per-game fallback
games/<game-id>/game-<buildId>.html per-game cache-busted build
games/<game-id>/game-manifest.json  per-game manifest
.nojekyll
README.md
```

## Games in this build

- `sprint-100m` — Sprint Master (v1)
- `throw-master` — Javelin Throw (v31)

## How it works

1. `index.html` (loader) fetches `manifest.json?t=<nonce>` with `cache: no-store`.
2. Loader reads `manifest.hub.file` and opens that hub HTML in a full-screen iframe.
3. Hub renders the game-picker, asks for player name, then opens a game's HTML
   (from `manifest.games[*].file`) in a nested iframe and communicates via
   `window.postMessage`. See `Docs/PLATFORM_PLAN.md`.

Source HTML versions, docs, Supabase function code, and tooling stay outside
the public release repository.
