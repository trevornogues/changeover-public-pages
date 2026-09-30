# changeover-public-pages

Public landing site for the [Changeover](https://github.com/trevornogues/changeover)
mobile app. Hosts the Privacy Policy and Terms of Service linked from the App
Store listing and (later) from Settings.

Served by GitHub Pages from the `main` branch root.

## Live URLs

- Index: <https://trevornogues.github.io/changeover-public-pages/>
- Changelog: <https://trevornogues.github.io/changeover-public-pages/changelog/>
- Privacy Policy: <https://trevornogues.github.io/changeover-public-pages/privacy/>
- Terms of Service: <https://trevornogues.github.io/changeover-public-pages/terms/>

The Privacy and Terms URLs are the ones to paste into App Store Connect.

## Structure

```
.
├── index.html              # Landing: hero + App Store CTA, features, pricing, FAQ, founder
├── changelog/
│   └── index.html          # Dated release notes (add a <article class="release"> per version)
├── privacy/
│   └── index.html          # Privacy Policy
├── terms/
│   └── index.html          # Terms of Service
├── assets/
│   ├── style.css           # Shared styles - tokens mirror Centre Lawn
│   ├── icon.png            # App court mark
│   ├── og-image.jpg        # 1200×630 social preview (icon on cream)
│   ├── favicon.png
│   ├── stripe-tile.png     # Brand stripe asset (reference)
│   └── screens/            # Store screenshots, cropped to the phone and downscaled to 640px
├── robots.txt              # Permissive; points at sitemap.xml
├── sitemap.xml             # Home, changelog, privacy, terms - add new pages here
├── llms.txt                # Plain-text product summary for AI assistants
├── .nojekyll               # Serve files as-is (no Jekyll)
└── README.md
```

## Keeping the landing page honest

- **App Store rating** in the hero (`.rating`) and in the JSON-LD `aggregateRating`
  is hand-copied from the listing. Refresh both after new reviews land.
- **Pricing** ($14.99/year, first month free) appears in the pricing section, the
  FAQ, the JSON-LD offers, `llms.txt`, and the changelog. Change all of them together.
- **Screenshots** in `assets/screens/` come from `changeover/store-listing/screenshots/`
  (crop the headline band off the top, resize to 640px wide, JPEG q82).
- **New releases**: add an entry to `changelog/index.html`, bump `softwareVersion`
  and `dateModified` in the JSON-LD, and update `lastmod` in `sitemap.xml`.
- `robots.txt` lives at `/changeover-public-pages/robots.txt` because this is a
  GitHub Pages project site; the domain-root `trevornogues.github.io/robots.txt`
  would have to come from a user-site repo.

## Brand

Visual tokens match the app's default **Centre Lawn** palette
(`#F5F3EC` cream, `#1C4A3A` pine, terracotta accent). The landing hero uses
the same court mark as the app icon, the Great Vibes **Changeover** wordmark,
and the cabana stripe ribbon - the same signature trio as Home in the app.


## Privacy posture (keep in sync with the app)

Changeover is local-first: the journal stays on device. There is no email/social
sign-up. Optional Changeover AI sends a **sanitized** history snapshot (other
people’s names → “Player A”) through Firebase Cloud Functions to OpenAI with
`store: false`. Changeover does not retain journal text on its servers; usage
counters and entitlement checks are keyed to a silent Firebase anonymous uid.
See `changeover/docs/PRODUCT_BRIEF.md` (“AI data pipeline” / “Privacy posture”).

## Deploy

Push to `main`. Pages is configured as: branch `main`, folder `/`.
