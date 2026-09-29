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

Hosted from the separate public repo `dayvo`, which holds a copy of this folder at its root.
Setup: **repo → Settings → Pages → Source: Deploy from a branch → `main` / `(root)`**. After
editing here, copy the changed files to that repo and push. URLs:

```
https://zainulabideen041.github.io/dayvo/
https://zainulabideen041.github.io/dayvo/privacy.html
https://zainulabideen041.github.io/dayvo/terms.html
https://zainulabideen041.github.io/dayvo/delete-account.html
```

`.nojekyll` makes Pages serve the files as-is instead of running them through Jekyll.

For the OAuth consent screen, add `zainulabideen041.github.io` under *Authorized domains*; Google
verification also asks you to verify it in Search Console (HTML-file method works on Pages).

## Editing

- Update the **Effective / Last updated** dates on both policies whenever the text changes.
- The policies describe what the code does (see `apps/backend/src/modules`). If you add an SDK
  (analytics, crash reporting, ads) or new data, update `privacy.html` and the Play Data safety form.
- Contact address used throughout: `mzainulabideen.rizvi@gmail.com`.
