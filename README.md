# zapdude-site

Download site for [Corvid](https://github.com/da1fs/corvid), the shielded
desktop chat hub for WhatsApp, Messenger and more (the project was
originally released as Zapdude; the rename is identity-only). Static,
dependency-free, vanilla HTML/CSS/JS.

License: **GNU AGPL-3.0** (see [LICENSE](./LICENSE) in this repository
and the full text in the main repo).

Live at: https://da1fs.github.io/zapdude-site/
(the old ldpf96.github.io address redirects here automatically)

## How it works

- GitHub Pages serves `index.html` from this repository root
  (branch `main`, folder `/`).
- Download buttons resolve at runtime through the GitHub API
  (`/repos/da1fs/corvid/releases/latest`), so they always point at the
  current release assets (`x64-setup.exe`, `aarch64.dmg`, `x64.dmg`).
  The visitor's platform gets a "recommended" outline; if the API is
  unreachable the buttons fall back to the Releases page.
- Two languages (Spanish default, English toggle) switch client side
  and persist in `localStorage` (key `zapdude-lang`, kept for
  compatibility).
- The page carries the project's heart section: why Corvid exists, the
  protection objectives (network allowlist shield, bundled free
  browser, honest local API) and the credit trail.
- macOS install notes on the page cover the one-time Gatekeeper
  confirmation for directly distributed apps (no paid Apple signing),
  and honestly note that the currently published build still installs
  as Zapdude.app until the first Corvid-branded release.

## Local preview

Open `index.html` in a browser, or serve the folder:

```powershell
python -m http.server 8000
```

## Publishing

Pushes to `main` rebuild the Pages site automatically. Pages is enabled
via the repository settings (source: main branch, root folder).
