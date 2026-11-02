# SCP: Containment Escape — Website

The game's English landing, privacy and terms pages. Plain static files: no framework, package install, build step or runtime API calls.

These files live in the game repository under `docs/web/`. The addresses below are planned ones; no public site exists yet.

- Site: https://durdenk.github.io/scp-escape-web/
- Privacy: https://durdenk.github.io/scp-escape-web/privacy-policy.html
- Terms: https://durdenk.github.io/scp-escape-web/terms-of-use.html
- Data deletion: https://durdenk.github.io/scp-escape-web/privacy-policy.html#data-deletion
- Google Play: https://play.google.com/store/apps/details?id=com.cukkacreatives.scp.containment.escape
- Android package: `com.cukkacreatives.scp.containment.escape`
- Developer: Cukka Creatives / Sait Maraslioglu
- Contact: cukkacreatives@gmail.com

## Local preview

```sh
python -m http.server 8765 --bind 127.0.0.1 --directory docs/web
```

Open http://127.0.0.1:8765/ and check landscape phone and desktop widths.

## Publishing

Publish the contents of this folder as a static site. Links are relative, so they work under a subpath. Enter the privacy and terms addresses in Google Play Console.

`.gdignore` keeps Godot from importing this folder into the game.

## Ads and data disclosures

The privacy policy and terms describe the current game: local saves only, with no ads, analytics, purchases or network permission. **Update them, and the Play Data safety form, before shipping a build that adds any of these.**

`app-ads.txt` holds the Cukka Creatives AdMob publisher line. AdMob looks for it at the root of the developer website's host, so a copy in this project subpath is not enough on its own: it must also be served at https://durdenk.github.io/app-ads.txt or from a custom domain's root.

## License

The site's text adapts SCP Wiki material and is offered under [CC BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/). Keep the credits section on the landing page in step with `STORY.md` section 10 at the repository root.
