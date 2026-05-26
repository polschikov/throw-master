# Throw Master

Pixel-art javelin rhythm runner with Supabase leaderboard and replay support.

## Deploy

This folder is the clean public GitHub Pages release. Upload the contents of this folder to the repository root:

- `index.html`
- `game.html`
- `game-<buildId>.html`
- `release.json`
- `.nojekyll`
- `README.md`

`index.html` is a small cache-busting loader. It fetches `release.json` with a fresh query string and then opens the hashed `game-<buildId>.html` file, so normal page refreshes pick up new releases quickly.

Source HTML versions, docs, Supabase function code, and tooling should stay outside the public release repository.

The public Supabase URL and publishable key are embedded in `index.html`. Do not add service-role or secret keys to this repository.
