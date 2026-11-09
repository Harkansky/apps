# apps (public pages)

Both stores require a privacy policy URL and a support URL for every app. This repo serves them for all your apps from one free GitHub Pages site.

## One-time setup

1. Create a **public** repo named `apps` and push this folder to it.
2. Settings → Pages → Source: "Deploy from a branch", branch `main`, folder `/ (root)`.
3. After a minute the site is live at `https://harkansky.github.io/apps/`.
4. Replace the placeholder name, contact email and GitHub user in `_config.yml`, `index.md` and `_app-template/`. The find-and-replace commands in the factory README ("Put it on GitHub", step 1) do this for you.

GitHub Pages is free for public repos. Your app repos can stay private.

## For each new app

```bash
cp -R _app-template <site_slug>      # same slug as app.config.yaml
```

Edit `<site_slug>/index.md` and `<site_slug>/privacy.md`, and their French versions in `<site_slug>/fr/` (app name, date, anything the app actually collects), add a line to `index.md`, push. The URLs to paste into the app and the stores are:

- Support: `https://harkansky.github.io/apps/<site_slug>/`
- Privacy: `https://harkansky.github.io/apps/<site_slug>/privacy/`

### French pages

`_app-template/fr/` holds French translations of both pages, and the template's bootstrap copies it along with the rest (so does the `cp -R` above). The French store listings link to:

- Support: `https://harkansky.github.io/apps/<site_slug>/fr/`
- Privacy: `https://harkansky.github.io/apps/<site_slug>/fr/privacy/`

Each page starts with a link to the other language. Keep the translations in sync: whenever you change an English page (in `_app-template/` or in an app's folder), make the same change to its French page, ads markers included.

The privacy text is a starting point for apps that work offline, sync saves only through the player's own iCloud or Google backup (see "Account sync" in the app_core README), sell store purchases and, by default, show optional rewarded ads through Google AdMob (with Google's consent form in the EEA, UK and Switzerland and Apple's tracking prompt on iPhone), nothing else. In `_app-template/`, ads-only text sits between `<!-- ads -->` and `<!-- /ads -->` lines, and text for apps without ads between `<!-- no-ads -->` and `<!-- /no-ads -->` lines. Each marker is on its own line and blocks are never nested. The template's bootstrap keeps the set that matches `ads.enabled` in `app.config.yaml`, deletes the other set and removes the marker lines, so an app with `ads.enabled: false` gets pages with no ads text at all. If you copy the folder by hand, do the same. If you add analytics, app accounts, a server or crash reporting, or change the ad setup, the policy, the App Store privacy labels and the Play Data safety form all need updating. This is not legal advice.
