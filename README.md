# corvid-site

Download site for [Corvid](https://github.com/da1fs/corvid), the shielded
desktop chat hub for WhatsApp, Messenger and more (the project was
originally released as Zapdude; the rename is identity-only). Static,
dependency-free, vanilla HTML/CSS/JS.

License: **GNU AGPL-3.0** (see [LICENSE](./LICENSE) in this repository
and the full text in the main repo).

Live at: https://da1fs.github.io/corvid-site/
(older addresses like ldpf96.github.io/zapdude-site are dead: GitHub
Pages does not redirect them; always publish the current URL)

## How it works

- GitHub Pages serves `index.html` from this repository root
  (branch `main`, folder `/`).
- Download buttons resolve at runtime through the GitHub API, scanning
  the releases list: each platform gets the newest release that
  actually carries its asset type (`x64-setup.exe` for Windows,
  `aarch64.dmg` / `x64.dmg` for macOS). If the newest tag shipped
  without macOS builds, the macOS buttons point at the last release
  that has them and the macOS card states which version it brings, so
  the page never offers a file that does not exist. If the API is
  unreachable the buttons fall back to the Releases page.
- Two languages (Spanish default, English toggle) switch client side
  and persist in `localStorage` (key `zapdude-lang`, kept for
  compatibility).
- The page carries the project's heart section: why Corvid exists, the
  protection objectives (network allowlist shield, bundled free
  browser, honest local API) and the credit trail.
- Install notes on the page cover the NSIS uninstall behavior (the data
  folder with the sessions is removed, copy it first), the macOS 13
  minimum, the Gatekeeper confirmation that repeats on every new
  downloaded build (unsigned, no paid Apple signing), and the honest
  note that the currently published build still installs as Zapdude.app
  until the first Corvid-branded release.

## Local preview

Open `index.html` in a browser, or serve the folder:

```powershell
python -m http.server 8000
```

## Publishing

Pushes to `main` rebuild the Pages site automatically. Pages is enabled
via the repository settings (source: main branch, root folder).
