# Brick Sort — Website

The game's English landing, privacy and terms pages. Plain static files: no
framework, package install, build step or runtime API calls.

- Public web repo: [durdenk/brick-sort-web](https://github.com/durdenk/brick-sort-web)
- Site: https://durdenk.github.io/brick-sort-web/
- Privacy: https://durdenk.github.io/brick-sort-web/privacy-policy.html
- Terms of use: https://durdenk.github.io/brick-sort-web/terms-of-use.html
- Data deletion: https://durdenk.github.io/brick-sort-web/privacy-policy.html#data-deletion
- Android package ID: `com.cukkacreatives.bricksort` (planned; there is no
  `export_presets.cfg` yet. If the export uses another ID, update the Google
  Play links in `index.html` and `info.md`.)
- Contact: cukkacreatives@gmail.com

More identity details are in [info.md](info.md). Store texts live in
`docs/store-listing/`.

## Local preview

From the project root:

```sh
python -m http.server 8765 --bind 127.0.0.1 --directory docs/web
```

Open http://127.0.0.1:8765/ and check it at phone width (about 390 px) and at
desktop width. Stop the server with Ctrl+C when done.

## Publishing on GitHub Pages

Copy these files to the **root of the public web repo**; do not publish the
private game repo or other project files:

- `index.html`
- `privacy-policy.html`
- `terms-of-use.html`
- `styles.css`
- `brick.svg`
- `bricks.svg`
- `app-ads.txt`
- `.nojekyll`

`README.md`, `info.md` and `.gdignore` stay here. `.gdignore` keeps Godot from
importing the website files into the game project.

The GitHub Pages source must be the `main` branch, `/ (root)`. Relative links
also work under the `/brick-sort-web/` sub-path. `brick.svg` (icon) and
`bricks.svg` (hero art) are drawn for this site in the game's brick colors.

After publishing, check the addresses above, then enter the privacy and terms
addresses in Google Play Console. Editing this folder does not update the
public repo or the live site by itself.

## Ads and data disclosures

The game will show ads (AdMob: interstitial and optional rewarded ads) and
sell optional in-app purchases through Google Play Billing (coin packs, coin
and boost bundles, a one-time Remove Ads). None of these are integrated yet;
the pages describe the planned release.

`app-ads.txt` holds the developer's AdMob publisher ID. Before release, check
it against the AdMob account used for this game. AdMob looks for
`/app-ads.txt` at the root of the developer website host; a copy under the
GitHub Pages project sub-path is not enough on its own. If `durdenk.github.io`
is the developer website, the same line must also be served at
https://durdenk.github.io/app-ads.txt. A custom domain with the file at its
root also works.

The privacy page also covers GameAnalytics and the Google Play in-app review
flow, which the release may use. When the integrations are done, make the
privacy page, the real SDK settings, the consent flow and the Google Play
Data safety form describe the same data practices; remove any section for a
service the release does not use.

The privacy page says the game is not directed at children under 13. If the
game is listed for children in Google Play's target audience, the Families
policy applies and the ads, analytics and privacy text must be reviewed again.

Official references:

- [Google Mobile Ads data disclosure](https://developers.google.com/admob/android/privacy/play-data-disclosure)
- [AdMob app-ads.txt setup](https://support.google.com/admob/answer/9363762)
- [GameAnalytics privacy notice](https://www.gameanalytics.com/trust/privacy-notice)
- [GameAnalytics data retention and deletion policy](https://www.gameanalytics.com/trust/data-retention-and-deletion-policy)
- [Google Play In-App Reviews](https://developer.android.com/guide/playcore/in-app-review#data-safety)
- [GitHub Pages and data collection](https://docs.github.com/en/pages/getting-started-with-github-pages/what-is-github-pages#data-collection)
