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

Edit `<site_slug>/index.md` and `<site_slug>/privacy.md` (app name, date, anything the app actually collects), add a line to `index.md`, push. The URLs to paste into the app and the stores are:

- Support: `https://harkansky.github.io/apps/<site_slug>/`
- Privacy: `https://harkansky.github.io/apps/<site_slug>/privacy/`

The privacy text is a starting point for apps that work offline, sync saves only through the player's own iCloud or Google backup (see "Account sync" in the app_core README), and sell store purchases, nothing else. If you add ads, analytics, app accounts, a server or crash reporting, the policy, the App Store privacy labels and the Play Data safety form all need updating. This is not legal advice.
