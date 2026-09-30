# Dark Console — Hermes Desktop

The Dark Console theme for the Hermes desktop app (the Electron app at
`apps/desktop` in the Hermes monorepo). One port in the
[dark-console](https://github.com/dark-console) suite; palette source of truth
is [`dark-console/core/palette.json`](https://github.com/dark-console/core/blob/master/palette.json).

## Install

```
hermes://plugin-desktop/install?repo=dark-console/hermes-desktop&force=true
```

or Settings → Plugins → **Install from Git** → `dark-console/hermes-desktop`.

Installs as a desktop plugin; hot-reloads on save. The theme then appears in
the Appearance picker under **Dark Console**, and ⌘K has
*Theme: apply Dark Console* + *Theme: copy Dark Console palette JSON*.

Existing installs of the upstream `barnacker/hermes_dark_studio` keep working
via the plugin's machine ID (`dark-studio`), which this port does not change.

## Contents

- `plugin.js` — one desktop plugin: the full `DesktopTheme` (THEMES_AREA) +
  scoped CSS for the elements no theme token reaches (maroon composer field,
  navy filled buttons / selected nav rows, italic thinking block, shiki token
  italics).
- `install.ps1` — PowerShell installer (Windows).

## Naming

- **Repo:** `dark-console/hermes-desktop` — the product name "Hermes Desktop".
- **Plugin ID/NAME:** `dark-studio` — unchanged from upstream, for
  backward-compat with install links and persisted selections.
- **Plugin LABEL (what you see):** `Dark Console`.

## Size / value audit

Every hex in `plugin.js` (`const V = {...}` + the `ANSI` block + scoped CSS)
should trace to `dark-console/core/palette.json`. Until the generator path
lands in this port, the drift-checker
(`dark-console/core/scripts/validate.py`) is the gate; this port follows the
one-off-artifact lane documented in `dark-console/vscode` while that
generator is built.

## License

MIT — see [LICENSE](LICENSE).
