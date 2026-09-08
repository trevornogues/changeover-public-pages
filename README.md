# changeover-public-pages

Public landing site for the [Changeover](https://github.com/trevornogues/changeover)
mobile app. Hosts the Privacy Policy and Terms of Service that the app links to
from its App Store listing and from inside Settings.

Served by GitHub Pages from the `main` branch root.

## Live URLs

Once GitHub Pages is enabled (Settings → Pages → Source: `Deploy from a branch`,
Branch: `main`, Folder: `/`), the pages live at:

- Index: <https://trevornogues.github.io/changeover-public-pages/>
- Privacy Policy: <https://trevornogues.github.io/changeover-public-pages/privacy/>
- Terms of Service: <https://trevornogues.github.io/changeover-public-pages/terms/>

These are the URLs to paste into App Store Connect.

## Structure

```
.
├── index.html              # Landing page with links to legal pages
├── privacy/
│   └── index.html          # Privacy Policy (TODO)
├── terms/
│   └── index.html          # Terms of Service (TODO)
├── assets/
│   └── style.css           # Shared styles — tokens mirror changeover/src/theme.js
├── .nojekyll               # Serve files as-is (no Jekyll)
└── README.md
```

## Status

Skeleton only. The privacy policy and terms still need to be written. Because
Changeover v0 is local-first with no accounts or backend, the privacy policy
should be short: data stays on device; no analytics in v0; the AI feature,
when added, will send sanitized tennis history to a model provider.
