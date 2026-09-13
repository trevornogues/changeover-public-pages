# changeover-public-pages

Public landing site for the [Changeover](https://github.com/trevornogues/changeover)
mobile app. Hosts the Privacy Policy and Terms of Service linked from the App
Store listing and (later) from Settings.

Served by GitHub Pages from the `main` branch root.

## Live URLs

- Index: <https://trevornogues.github.io/changeover-public-pages/>
- Privacy Policy: <https://trevornogues.github.io/changeover-public-pages/privacy/>
- Terms of Service: <https://trevornogues.github.io/changeover-public-pages/terms/>

These are the URLs to paste into App Store Connect.

## Structure

```
.
├── index.html              # Landing page with links to legal pages
├── privacy/
│   └── index.html          # Privacy Policy
├── terms/
│   └── index.html          # Terms of Service
├── assets/
│   └── style.css           # Shared styles — tokens mirror Club Green
├── .nojekyll               # Serve files as-is (no Jekyll)
└── README.md
```

## Privacy posture (keep in sync with the app)

Changeover is local-first: the journal stays on device. There is no email/social
sign-up. Optional Changeover AI sends a **sanitized** history snapshot (other
people’s names → “Player A”) through Firebase Cloud Functions to OpenAI with
`store: false`. Changeover does not retain journal text on its servers; usage
counters and entitlement checks are keyed to a silent Firebase anonymous uid.
See `changeover/docs/PRODUCT_BRIEF.md` (“AI data pipeline” / “Privacy posture”).

## Deploy

Push to `main`. Pages is configured as: branch `main`, folder `/`.
