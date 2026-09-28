# Dayvo legal site

Static HTML + CSS (no build step) for the public pages the stores and Google require. Styled with the
app's design tokens (Green theme, Plus Jakarta Sans, soft cards, pill buttons, hatched bars).

| Page | File | Used for |
|---|---|---|
| Homepage | `index.html` | Google OAuth consent screen → *App home page* |
| Privacy Policy | `privacy.html` | OAuth consent screen, Play Console *App content → Privacy policy*, App Store Connect |
| Terms of Service | `terms.html` | OAuth consent screen → *Terms of service*, App Store (custom EULA, optional) |
| Delete account | `delete-account.html` | Play Console *Data safety → Delete account URL* |

## Publishing (GitHub Pages)

`.github/workflows/legal-pages.yml` deploys this folder on every push to `main` that touches it.
One-time setup: **GitHub repo → Settings → Pages → Source: GitHub Actions**, then push (or run the
workflow manually). URLs:

```
https://zainulabideen041.github.io/Schedule-App/
https://zainulabideen041.github.io/Schedule-App/privacy.html
https://zainulabideen041.github.io/Schedule-App/terms.html
https://zainulabideen041.github.io/Schedule-App/delete-account.html
```

GitHub Pages on a **private** repository needs a paid GitHub plan. Otherwise, copy this folder to a
separate public repo and enable Pages there (Source: deploy from branch, root).

For the OAuth consent screen, add `zainulabideen041.github.io` under *Authorized domains*; Google
verification also asks you to verify it in Search Console (HTML-file method works on Pages).

## Editing

- Update the **Effective / Last updated** dates on both policies whenever the text changes.
- The policies describe what the code does (see `apps/backend/src/modules`). If you add an SDK
  (analytics, crash reporting, ads) or new data, update `privacy.html` and the Play Data safety form.
- Contact address used throughout: `mzainulabideen.rizvi@gmail.com`.
